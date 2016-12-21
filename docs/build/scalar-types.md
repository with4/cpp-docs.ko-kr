---
title: "스칼라 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 스칼라 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

어떠한 맞춤에서도 데이터를 액세스할 수 있지만 성능 저하나 복잡성을 피하기 위해서는 데이터를 원래 경계에 따라 맞추는 것이 좋습니다.  열거형은 상수 정수이며 32비트 정수로 취급됩니다.  다음 표에서는 형식 정의와 함께 각 형식이 사용하는 아래와 같은 맞춤 값에 따라 권장되는 저장소를 보여 줍니다.  
  
-   Byte – 8비트  
  
-   Word – 16비트  
  
-   Double Word – 32비트  
  
-   Quad Word – 64비트  
  
-   Octa Word – 128비트  
  
|||||  
|-|-|-|-|  
|스칼라 형식|C 데이터 형식|저장소 크기\(바이트\)|권장되는 맞춤|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16**|**short**|2|Word|  
|**UINT16**|**unsigned short**|2|Word|  
|**INT32**|**int, long**|4|Doubleword|  
|**UINT32**|**unsigned int, unsigned long**|4|Doubleword|  
|**INT64**|`__int64`|8|Quadword|  
|**UINT64**|**unsigned \_\_int64**|8|Quadword|  
|**FP32\(단정밀도\)**|**float**|4|Doubleword|  
|**FP64\(배정밀도\)**|**double**|8|Quadword|  
|**POINTER**|**\***|8|Quadword|  
|`__m64`|**struct \_\_m64**|8|Quadword|  
|`__m128`|**struct \_\_m128**|16|Octaword|  
  
## 참고 항목  
 [형식 및 저장소](../build/types-and-storage.md)