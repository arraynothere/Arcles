---
title: "Parsing Metadata & Protobuf Structures in Android Runtime"
date: 2026-10-27T22:00:00+07:00
draft: false
tags: ["java", "android", "protobuf", "snippet"]
categories: ["Engineering"]
---

Ketika melakukan reverse engineering atau parsing struktur objek di dalam framework Android runtime, kita seringkali berurusan dengan skema `Protocol Buffers` (Protobuf) dan fungsi internal native. 

Berikut adalah contoh snippet representasi pesan Protobuf sederhana yang mendefinisikan `ContentType` dan metadata objek:

```protobuf
message AIRichResponseContentItemsMetadata {
    enum ContentType {
        DEFAULT = 0;
        CAROUSEL = 1;
    }

    message AIRichResponseReelItem {
        optional string title = 1;
        optional string profileIconURL = 2;
        optional string thumbnailURL = 3;
        optional string videoURL = 4;
    }

    repeated AIRichResponseContentItemsMetadata items = 1;
    optional ContentType contentType = 2;
}
```

### Analisis Fungsi Native (`__int64`)

Ketika di-cross-reference melalui disassembler, fungsi penanganan metadata tersebut seringkali mengembalikan pointer 64-bit (`__int64`) dengan struktur register cepat (`__fastcall`):

```cpp
__int64 __fastcall sub_101AF22F0(__int64 a1)
{
    __int64 v1; // x30
    int v2;      // w0
    
    // Inisialisasi pointer dan parsing buffer lokal
    v1 = *(_QWORD *)(a1 + 16);
    v2 = *(unsigned int *)(a1 + 24);
    
    return v1 + v2;
}
```

Snippet di atas menunjukkan bagaimana argumen register dipetakan ke dalam variabel lokal sebelum kalkulasi pointer dieksekusi. Sangat efisien untuk optimasi tingkat rendah.
