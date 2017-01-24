---
title: "include_alias | Microsoft Docs"
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
  - "vc-pragma.include_alias"
  - "include_alias_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "include_alias pragma"
  - "pragma, include_alias"
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# include_alias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*short\_filename*을 *long\_filename*의 별칭으로 사용하도록 지정합니다.  
  
## 구문  
  
```  
  
      #pragma include_alias( "  
      long_filename  
      ", "  
      short_filename  
      " )  
#pragma include_alias( <long_filename>, <short_filename> )  
```  
  
## 설명  
 일부 파일 시스템의 경우 8.3 FAT 파일 시스템 제한보다 더 긴 헤더 파일 이름을 가질 수 있습니다.  더 긴 헤더 파일 이름의 첫 8개 문자가 고유하지 않을 수 있기 때문에 컴파일러는 더 긴 이름을 8.3으로 간단히 자를 수 없습니다.  컴파일러가 *long\_filename* 문자열을 확인할 때마다 해당 문자열을 *short\_filename*으로 대체한 후 *short\_filename* 헤더 파일을 찾습니다.  이 pragma는 해당 `#include` 지시문 앞에 배치되어야 합니다.  예를 들면 다음과 같습니다.  
  
```  
// First eight characters of these two files not unique.  
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )  
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )  
  
#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )  
  
#include "AppleSystemHeaderQuickdraw.h"  
#include "AppleSystemHeaderFruit.h"  
#include "GraphicsMenu.h"  
```  
  
 검색된 별칭은 철자, 큰따옴표 또는 꺾쇠 괄호 사용에서 지정된 내용과 정확하게 일치해야 합니다.  **Include\_alias** pragma는 파일 이름에 대해 간단한 문자열 일치를 검사하며 그 외의 파일 이름 유효성 검사는 수행하지 않습니다.  예를 들어 다음과 같은 지시문에서는  
  
```  
#pragma include_alias("mymath.h", "math.h")  
#include "./mymath.h"  
#include "sys/mymath.h"  
```  
  
 헤더 파일 문자열이 정확하게 일치하지 않기 때문에 별칭 대체가 수행되지 않습니다.  또한 \/Yu 및 \/Yc 컴파일러 옵션 또는 **hdrstop** pragma에 대한 인수로 사용되는 헤더 파일 이름도 대체되지 않습니다.  예를 들어 소스 파일에 다음 지시문이 포함된 경우,  
  
```  
#include <AppleSystemHeaderStop.h>  
```  
  
 해당 컴파일러 옵션은 다음과 같이 됩니다.  
  
```  
/YcAppleSystemHeaderStop.h  
```  
  
 **include\_alias** pragma를 사용하여 헤더 파일 이름을 다른 이름으로 매핑할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
#pragma include_alias( "api.h", "c:\version1.0\api.h" )  
#pragma include_alias( <stdio.h>, <newstdio.h> )  
#include "api.h"  
#include <stdio.h>  
```  
  
 큰따옴표로 묶인 파일 이름과 꺾쇠 괄호로 묶인 파일 이름을 섞어 사용하지 마십시오.  예를 들어 위의 두 가지 **\#pragma include\_alias** 지시문이 주어진 경우 컴파일러는 다음 `#include` 지시문에서 대체를 수행하지 않습니다.  
  
```  
#include <api.h>  
#include "stdio.h"  
```  
  
 또한 다음 지시문은 오류를 생성합니다.  
  
```  
#pragma include_alias(<header.h>, "header.h")  // Error  
```  
  
 오류 메시지로 보고되거나 미리 정의된 **\_\_FILE\_\_** 매크로의 값으로 보고된 파일 이름은 대체가 수행된 후의 파일 이름입니다.  예를 들어 다음 지시문 뒤에  
  
```  
#pragma include_alias( "VeryLongFileName.H", "myfile.h" )  
#include "VeryLongFileName.H"  
```  
  
 VERYLONGFILENAME.H의 오류는 다음 오류 메시지를 생성합니다.  
  
```  
myfile.h(15) : error C2059 : syntax error  
```  
  
 또한 전이성은 지원되지 않습니다.  다음과 같은 지시문이 주어진 경우  
  
```  
#pragma include_alias( "one.h", "two.h" )  
#pragma include_alias( "two.h", "three.h" )  
#include "one.h"  
```  
  
 컴파일러는 THREE.H가 아니라 TWO.H 파일을 검색합니다.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)