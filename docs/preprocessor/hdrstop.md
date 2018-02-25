---
title: hdrstop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
dev_langs:
- C++
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18216663524c48e4ec4ee327ff096c8b3dbd391c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="hdrstop"></a>hdrstop
사전 컴파일 파일 이름과 컴파일 상태가 저장되는 위치에 대한 추가적 제어를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma hdrstop [( "filename" )]    
```  
  
## <a name="remarks"></a>설명  
 *filename* 사용 하거나 만들 미리 컴파일된 헤더 파일의 이름 (인지 여부에 따라 [/Yu](../build/reference/yu-use-precompiled-header-file.md) 또는 [/Yc](../build/reference/yc-create-precompiled-header-file.md) 지정). 경우 *filename* 경로 지정을는 미리 컴파일된 헤더 파일이 소스 파일과 동일한 디렉터리에 있는 것으로 간주 됩니다.  
  
 C 또는 c + + 파일에 포함 된 경우는 **hdrstop** /Yc로 컴파일될 때 pragma를 사용 하면 컴파일러의 pragma의 위치까지 컴파일 상태를 저장 합니다. pragma 뒤에 오는 모든 코드의 컴파일된 상태는 저장되지 않습니다.  
  
 사용 하 여 *filename* 컴파일된 상태가 저장 되어 있는 미리 컴파일된 헤더 파일 이름을 지정 합니다. 사이 공백을 **hdrstop** 및 *filename* 선택 사항입니다. 지정 된 파일 이름이 **hdrstop** pragma은 문자열 이므로 모든 C 또는 c + + 문자열의 제약 조건에 따릅니다. 특히, 이름을 따옴표로 묶고 이스케이프 문자(백슬래시)를 사용하여 디렉터리 이름을 지정해야 합니다. 예:  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
 미리 컴파일된 헤더 파일의 이름은 다음 규칙에 따라 우선 순위대로 결정됩니다.  
  
1.  /Fp 컴파일러 옵션에 대한 인수  
  
2.  *filename* # 인수**pragma hdrstop**  
  
3.  확장명이 .PCH인 소스 파일의 기본 이름  
  
 /Yc 및 /Yu 옵션 경우 두 개의 컴파일 옵션 모두에 대 한와 **hdrstop** pragma는 파일 이름 지정, 소스 파일의 기본 이름 미리 컴파일된 헤더 파일의 기본 이름으로 사용 됩니다.  
  
 다음과 같이 전처리 명령을 사용하여 매크로 대체를 수행할 수도 있습니다.  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
 다음 규칙에 따라 위치는 **hdrstop** pragma를 배치 될 수 있습니다.  
  
-   hdrstop pragma가 데이터나 함수 선언 또는 정의 외부에 나타나야 합니다.  
  
-   hdrstop pragma가 헤더 파일 내부가 아닌 소스 파일에 지정되어야 합니다.  
  
## <a name="example"></a>예  
  
```  
#include <windows.h>                 // Include several files  
#include "myhdr.h"  
  
__inline Disp( char *szToDisplay )   // Define an inline function  
{  
    ...                              // Some code to display string  
}  
#pragma hdrstop  
```  
  
 이 예제는 **hdrstop** pragma가 두 개의 파일이 포함 되 고 인라인 함수를 정의한 후 나타납니다. 언뜻 보면 pragma의 위치가 이상할 수 있습니다. 하지만 사용해봅니다, 해당 수동 미리 컴파일 옵션인 /Yc 및 /Yu와 **hdrstop** pragma를 사용 하면 전체 소스 파일을 미리 컴파일할 수 있습니다-심지어 인라인 코드도 합니다. Microsoft 컴파일러는 데이터 선언만 미리 컴파일하도록 제한하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)