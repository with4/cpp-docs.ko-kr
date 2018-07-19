---
title: 스칼라 형식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5490bb33cafd8d2942e434ab9c50e34441506463
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381173"
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
|`__m64`|**struct __m64**|8|쿼드 워드|  
|`__m128`|**struct __m128**|16|Octaword|  
  
## <a name="see-also"></a>참고 항목  
 [형식 및 저장소](../build/types-and-storage.md)