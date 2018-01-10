---
title: "집계 및 공용 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: aggregates [C++], and unions
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 74ee1bbcf1a39171b18c09274543c72e0b844748
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="aggregates-and-unions"></a>집계 및 공용 구조체
배열, 구조체 및 공용 구조체와 같은 다른 형식에는 일관성 있는 집계 및 공용 구조체 저장소 및 데이터 검색을 보장 하는 보다 엄격한 맞춤 요구 사항이 있습니다. 배열, 구조체 및 공용 구조체에 대 한 정의 다음과 같습니다.  
  
 배열  
 인접 한 데이터 개체의 정렬된 된 그룹을 포함합니다. 각 개체에 요소를 라고 합니다. 배열 내에서 모든 요소는 동일한 크기 및 데이터 유형을 갖습니다.  
  
 구조체  
 데이터 개체의 정렬된 된 그룹을 포함합니다. 배열 요소와 달리 구조체 내의 데이터 개체는 서로 다른 데이터 형식 및 크기를 가질 수 있습니다. 구조체의 각 데이터 개체 멤버를 라고 합니다.  
  
 공용 구조체  
 명명 된 멤버 집합 중 하나를 보유 하는 개체입니다. 명명된 된 집합의 구성원은 모든 형식의 수 있습니다. 공용 구조체에 할당 된 저장소는 해당 공용 구조체 맞춤에 필요한 안쪽 여백을 더한 크기의 최대 멤버에 필요한 저장소와 같습니다.  
  
 다음 표에서 공용 구조체 및 구조체의 스칼라 멤버에 대 한 권장 되는 맞춤이 보여 줍니다.  
  
||||  
|-|-|-|  
|스칼라 형식|C 데이터 형식|필수 맞춤|  
|**INT8**|`char`|Byte|  
|**UINT8**|`unsigned char`|Byte|  
|**INT16**|**short**|단어|  
|**UINT16**|**unsigned short**|단어|  
|**INT32**|**int, long**|워드 단위|  
|**UINT32**|**부호 없는 int, 부호 없는 long**|워드 단위|  
|**INT64**|`__int64`|쿼드 워드|  
|**UINT64**|**unsigned __int64**|쿼드 워드|  
|**FP32 (정밀도 단일)**|**float**|워드 단위|  
|**FP64 (이중 정밀도)**|**double**|쿼드 워드|  
|**포인터**|**\***|쿼드 워드|  
|`__m64`|**__m64 구조체**|쿼드 워드|  
|`__m128`|**__m128 구조체**|Octaword|  
  
 다음 집계 정렬 규칙이 적용 됩니다.  
  
-   배열 정렬 된 배열의 요소 중 하나의 맞춤와 같습니다.  
  
-   시작 하는 구조체 또는 공용 구조체의 맞춤은 개별 멤버의 최대 맞춤. 구조체 또는 공용 구조체 내에서 각 멤버는 암시적 내부, 이전 멤버에 따라 위의 표에 정의 된 대로 적절 한 맞춤에 배치 되어야 합니다.  
  
-   구조 크기, 안쪽 여백 마지막 멤버 뒤에 필요할 수 있는 맞춤의 배수가 이어야 합니다. 구조체 및 공용 구조체 배열에 그룹화 할 수 있습니다, 때문 구조체 또는 공용 구조체의 각 배열 요소 시작 하 고 이전에 확인 적절 한 맞춤에서 끝나야 합니다.  
  
-   데이터 정렬 요구 사항 보다 큰 것으로 위의 규칙을 준수 하는 방식에 맞게 것 같습니다.  
  
-   개별 컴파일러 크기 문제로 인해 구조의 압축을 조정할 수 있습니다. 예를 들어 [/Zp (구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md) 구조체의 압축을 조정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [형식 및 저장소](../build/types-and-storage.md)