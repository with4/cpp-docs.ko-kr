---
title: "스칼라 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15b0915637025e176ee98d01be3991b30b4e6544
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="scalar-types"></a>스칼라 형식
데이터의 액세스를 모든 맞춤에서 발생할 수 있습니다, 있지만 데이터 성능 손실 (또는 복잡성)을 방지 하기 위해 해당 자연 경계에 정렬 될 것이 좋습니다. 열거형 상수 정수가 고 32 비트 정수로 처리 됩니다. 다음 표에서 맞춤 다음 맞춤 값을 사용 하 여 관련 된 것에 대 한 형식 정 및 권장 되는 저장소 설명:  
  
-   바이트-8 비트  
  
-   16 비트 단어-  
  
-   32 비트 2 배 워드-  
  
-   쿼드 단어-64 비트  
  
-   Octa 단어-128 비트  
  
|||||  
|-|-|-|-|  
|스칼라 형식|C 데이터 형식|저장소 크기 (바이트)|권장 되는 맞춤|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16**|**short**|2|단어|  
|**UINT16**|**unsigned short**|2|단어|  
|**INT32**|**int, long**|4|워드 단위|  
|**UINT32**|**부호 없는 int, 부호 없는 long**|4|워드 단위|  
|**INT64**|`__int64`|8|쿼드 워드|  
|**UINT64**|**unsigned __int64**|8|쿼드 워드|  
|**FP32 (정밀도 단일)**|**float**|4|워드 단위|  
|**FP64 (이중 정밀도)**|**double**|8|쿼드 워드|  
|**포인터**|**\***|8|쿼드 워드|  
|`__m64`|**__m64 구조체**|8|쿼드 워드|  
|`__m128`|**__m128 구조체**|16|Octaword|  
  
## <a name="see-also"></a>참고 항목  
 [형식 및 저장소](../build/types-and-storage.md)