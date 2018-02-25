---
title: "최적화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae1988292b1f6dfa35f4cb77d145641528ed827f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="optimize"></a>optimize
함수별로 수행할 최적화를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## <a name="remarks"></a>설명  
 **최적화** pragma는 함수 외부에 나타나야 하며 pragma가 표시 된 후 정의 된 첫 번째 함수에 적용 됩니다. **에** 및 **오프** 에 지정 된 옵션을 설정 하는 인수는 *최적화 목록* 설정 하거나 해제 합니다.  
  
 *최적화 목록* 0 개 이상의 다음 표에 표시 된 매개 변수가 될 수 있습니다.  
  
### <a name="parameters-of-the-optimize-pragma"></a>optimize Pragma의 매개 변수  
  
|매개 변수|최적화 형식|  
|--------------------|--------------------------|  
|**g**|전역 최적화를 활성화합니다.|  
|**s** 또는 **t**|짧거나 빠른 기계어 코드 시퀀스를 지정합니다.|  
|**y**|프로그램 스택에서 프레임 포인터를 생성합니다.|  
  
 이들은 함께 사용할 동일한 문자는 [/O](../build/reference/o-options-optimize-code.md) 컴파일러 옵션입니다. 예를 들어 다음 pragma는 해당 하는 **/Os** 컴파일러 옵션:  
  
```  
#pragma optimize( "ts", on )  
```  
  
 사용 하는 **최적화** pragma를 빈 문자열 (**""**)는 특별 한 형태의 지시문:  
  
 사용 하는 경우는 **오프** 매개 변수를 해제이 항목 앞부분의 표에 나열 된 최적화를 설정 합니다.  
  
 사용 하는 경우는 **에** 매개 변수를 최적화를 재설정 사용 하 여 지정한는 [/O](../build/reference/o-options-optimize-code.md) 컴파일러 옵션입니다.  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)