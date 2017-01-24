---
title: "hdrstop | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "hdrstop_CPP"
  - "vc-pragma.hdrstop"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "hdrstop pragma"
  - "pragma, hdrstop"
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hdrstop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사전 컴파일 파일 이름과 컴파일 상태가 저장되는 위치에 대한 추가적 제어를 제공합니다.  
  
## 구문  
  
```  
  
#pragma hdrstop [( "filename" )]    
```  
  
## 설명  
 *filename*은 [\/Yu](../build/reference/yu-use-precompiled-header-file.md)가 지정되었는지, 아니면 [\/Yc](../build/reference/yc-create-precompiled-header-file.md)가 지정되었는지에 따라 사용하거나 만들 미리 컴파일된 헤더 파일의 이름입니다.  *filename*에 경로 지정을 포함하지 않으면 미리 컴파일된 헤더 파일이 소스 파일과 동일한 디렉터리에 있는 것으로 간주됩니다.  
  
 \/Yc로 컴파일될 때 C 또는 C\+\+ 파일에 **hdrstop** pragma가 포함되어 있으면 컴파일러가 pragma의 위치까지 컴파일 상태를 저장합니다.  pragma 뒤에 오는 모든 코드의 컴파일된 상태는 저장되지 않습니다.  
  
 컴파일된 상태가 저장되는 미리 컴파일된 헤더 파일의 이름을 지정하려면 *filename*을 사용하십시오.  **hdrstop**과 *filename* 사이의 공백은 선택 사항입니다.  **hdrstop** pragma에 지정되는 파일 이름은 문자열이므로 모든 C 또는 C\+\+ 문자열의 제약 조건을 따릅니다.  특히, 이름을 따옴표로 묶고 이스케이프 문자\(백슬래시\)를 사용하여 디렉터리 이름을 지정해야 합니다.  예를 들면 다음과 같습니다.  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
 미리 컴파일된 헤더 파일의 이름은 다음 규칙에 따라 우선 순위대로 결정됩니다.  
  
1.  \/Fp 컴파일러 옵션에 대한 인수  
  
2.  \#**pragma hdrstop**에 대한 *filename* 인수  
  
3.  확장명이 .PCH인 소스 파일의 기본 이름  
  
 \/Yc 및 \/Yu 옵션의 경우 두 컴파일 옵션과 **hdrstop** pragma 모두 파일 이름을 지정하지 않으면 소스 파일의 기본 이름이 미리 컴파일된 헤더 파일의 기본 이름으로 사용됩니다.  
  
 다음과 같이 전처리 명령을 사용하여 매크로 대체를 수행할 수도 있습니다.  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
 **hdrstop** pragma를 배치할 수 있는 위치는 다음 규칙에 따라 결정됩니다.  
  
-   hdrstop pragma가 데이터나 함수 선언 또는 정의 외부에 나타나야 합니다.  
  
-   hdrstop pragma가 헤더 파일 내부가 아닌 소스 파일에 지정되어야 합니다.  
  
## 예제  
  
```  
#include <windows.h>                 // Include several files  
#include "myhdr.h"  
  
__inline Disp( char *szToDisplay )   // Define an inline function  
{  
    ...                              // Some code to display string  
}  
#pragma hdrstop  
```  
  
 이 예제에서는 두 파일이 포함되고 인라인 함수가 정의된 후에 **hdrstop** pragma가 나타납니다.  언뜻 보면 pragma의 위치가 이상할 수 있습니다.  그러나 **hdrstop** pragma에 수동 미리 컴파일 옵션인 \/Yc 및 \/Yu를 사용하면 전체 소스 파일, 심지어 인라인 코드도 미리 컴파일할 수 있다는 사실을 생각해 보십시오.  Microsoft 컴파일러는 데이터 선언만 미리 컴파일하도록 제한하지 않습니다.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)