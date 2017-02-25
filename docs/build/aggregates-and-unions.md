---
title: "집계 및 공용 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "집계[C++], 공용 구조체"
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 집계 및 공용 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

배열, 구조체 및 공용 구조체 같은 기타 형식의 경우 집계 및 공용 구조체 저장소와 데이터 검색을 일관되게 유지하기 위해 더 엄격한 맞춤 요구 사항을 충족해야 합니다.  다음은 배열, 구조체 및 공용 구조체에 대한 정의입니다.  
  
 배열  
 인접한 데이터 개체의 순서가 지정된 그룹이 들어 있습니다.  각 개체를 요소라고 합니다.  배열의 모든 요소는 크기와 데이터 형식이 동일합니다.  
  
 구조체  
 데이터 개체의 순서가 지정된 그룹이 들어 있습니다.  배열의 요소와 달리 구조체의 데이터 개체는 데이터 형식과 크기가 서로 다를 수 있습니다.  구조체의 각 데이터 개체를 멤버라고 합니다.  
  
 공용 구조체  
 명명된 멤버 집합 하나가 저장된 개체입니다.  명명된 집합의 멤버는 임의의 형식일 수 있습니다.  공용 구조체에 할당된 저장소의 크기는 해당 공용 구조체의 가장 큰 멤버에 필요한 저장소와 맞춤에 필요한 안쪽 여백을 더한 크기에 해당합니다.  
  
 다음 표에는 공용 구조체와 구조체의 스칼라 멤버에 권장되는 맞춤이 나와 있습니다.  
  
||||  
|-|-|-|  
|스칼라 형식|C 데이터 형식|필요한 맞춤|  
|**INT8**|`char`|Byte|  
|**UINT8**|`unsigned char`|Byte|  
|**INT16**|**short**|Word|  
|**UINT16**|**unsigned short**|Word|  
|**INT32**|**int, long**|Doubleword|  
|**UINT32**|**unsigned int, unsigned long**|Doubleword|  
|**INT64**|`__int64`|Quadword|  
|**UINT64**|**unsigned \_\_int64**|Quadword|  
|**FP32\(단정밀도\)**|**float**|Doubleword|  
|**FP64\(배정밀도\)**|**double**|Quadword|  
|**POINTER**|**\***|Quadword|  
|`__m64`|**struct \_\_m64**|Quadword|  
|`__m128`|**struct \_\_m128**|Octaword|  
  
 여기에 적용되는 집계 맞춤 규칙은 다음과 같습니다.  
  
-   배열 맞춤은 배열 요소 중 하나의 맞춤과 동일합니다.  
  
-   구조체나 공용 구조체의 시작 부분 맞춤은 개별 멤버의 최대 맞춤입니다.  구조체나 공용 구조체 내의 각 멤버는 위 표에서 정의한 대로 적절한 맞춤에 따라 배치해야 합니다. 이 경우 이전 멤버에 따라 암시적 내부 안쪽 여백이 필요할 수도 있습니다.  
  
-   구조체 크기는 해당 맞춤의 배수여야 합니다. 이 경우 마지막 멤버 뒤에 안쪽 여백이 필요할 수도 있습니다.  구조체와 공용 구조체는 배열에 그룹화될 수 있으므로 구조체나 공용 구조체의 각 배열 요소는 이전에 결정된 적절한 맞춤에 따라 시작하고 끝나야 합니다.  
  
-   위의 규칙을 준수하는 한 맞춤 요구 사항보다 큰 방식으로 데이터를 맞출 수 있습니다.  
  
-   크기 문제로 인해 개별 컴파일러에서 구조체의 압축을 조정할 수도 있습니다.  예를 들어, [\/Zp\(구조체 멤버 맞춤\)](../build/reference/zp-struct-member-alignment.md)를 사용하여 구조체의 압축을 조정할 수 있습니다.  
  
## 참고 항목  
 [형식 및 저장소](../build/types-and-storage.md)