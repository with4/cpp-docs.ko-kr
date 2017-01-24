---
title: "#include 지시문 (C/C++) | Microsoft Docs"
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
  - "#include"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#include 지시문"
  - "include 지시문(#include)"
  - "전처리기, 지시문"
ms.assetid: 17067dc0-8db1-4f2d-b43e-ec12ecf83238
caps.latest.revision: 15
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #include 지시문 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

소스 프로그램에서 지시문이 표시된 지점에 지정된 파일의 내용이 표시된 것처럼 해당 파일의 내용을 처리하도록 전처리기에 지시합니다.  
  
## 구문  
  
```  
  
      #include  "path-spec"  
#include  <path-spec>  
```  
  
## 설명  
 include 파일에 상수 및 매크로 정의를 정리한 후 `#include` 지시문을 사용하여 해당 정의를 소스 파일에 추가할 수 있습니다.  include 파일은 외부 변수와 복잡한 데이터 형식의 선언을 통합하는 데 유용합니다.  형식은 해당 목적으로 만든 include 파일에서 한 번만 정의하고 명명하면 됩니다.  
  
 `path-spec`은 선택적으로 디렉터리 사양 뒤에 올 수 있는 파일 이름입니다.  이 파일 이름은 기존 파일의 이름이어야 합니다.  `path-spec`의 구문은 프로그램이 컴파일되는 운영 체제에 따라 달라집니다.  
  
 [\/clr](../build/reference/clr-common-language-runtime-compilation.md)을 사용하여 컴파일된 C\+\+ 응용 프로그램에서 어셈블리를 참조하는 방법에 대한 자세한 내용은 [\#using](../preprocessor/hash-using-directive-cpp.md)을 참조하십시오.  
  
 두 구문 형식은 지시문을 지정된 include 파일의 전체 내용으로 바꿉니다.  경로가 불완전하게 지정되어 있을 경우 두 형식의 차이는 전처리기가 헤더 파일을 검색하는 순서입니다.  다음 표에서는 두 구문 형식 간 차이를 보여 줍니다.  
  
|구문 형식|작업|  
|-----------|--------|  
|따옴표로 묶인 형식|전처리기는 다음 순서로 include 파일을 검색합니다.<br /><br /> 1.  `#include` 문이 포함된 파일과 동일한 디렉터리를 검색합니다.<br />2.  현재 열려 있는 include 파일의 디렉터리에서 include 파일이 열린 반대 순서로 검색합니다.  검색은 부모 include 파일의 디렉터리에서 시작하여 위쪽의 상위 부모 include 파일 디렉터리로 진행됩니다.<br />3.  각 \/I 컴파일러 옵션에 지정된 경로를 따라 검색합니다.<br />4.  INCLUDE 환경 변수에서 지정한 경로를 따라 검색합니다.|  
|꺾쇠 괄호 형식|전처리기는 다음 순서로 include 파일을 검색합니다.<br /><br /> 1.  각 \/I 컴파일러 옵션에 지정된 경로를 따라 검색합니다.<br />2.  명령줄에서 컴파일하는 경우, INCLUDE 환경 변수에서 지정한 경로를 따라 검색합니다.|  
  
 전처리기가 지정된 이름의 파일을 찾는 즉시 검색이 중단됩니다.  완전하고 명확한 include 파일의 경로 지정이 큰따옴표\(" "\)로 묶인 경우 전처리기는 해당 경로 지정만 검색하고 표준 디렉터리를 무시합니다.  
  
 큰따옴표로 묶인 파일 이름이 불완전한 경로 지정인 경우 전처리기에서는 먼저 "부모" 파일의 디렉터리를 검색합니다.  부모 파일은 `#include` 지시문을 포함하는 파일입니다.  예를 들어 `file1` 파일 내에 `file2` 파일이 포함된 경우 `file1`이 부모 파일입니다.  
  
 Include 파일은 "중첩"될 수 있습니다. 즉, `#include` 지시문은 다른 `#include` 지시문에 의해 이름이 지정된 파일에 표시될 수 있습니다.  예를 들어, `file2`는 `file3`을 포함할 수 있습니다.  이 경우 `file1`은 여전히 `file2`의 부모 파일이지만 `file3`의 "상위 부모" 파일도 됩니다.  
  
 include 파일이 중첩되고 명령줄에서 컴파일이 실행될 경우 디렉터리 검색은 부모 파일의 디렉터리에서 시작하여 상위 부모 파일의 디렉터리로 진행됩니다.  즉, 현재 처리 중인 소스가 포함된 디렉터리를 기준으로 검색이 시작됩니다.  파일이 없으면 \/I 컴파일러 옵션에서 지정한 디렉터리로 이동하여 검색합니다.  마지막으로 INCLUDE 환경 변수에 지정된 디렉터리가 검색됩니다.  
  
 개발 환경에서는 INCLUDE 환경 변수가 무시됩니다.  include 파일 검색 디렉터리를 설정하는 방법에 대한 자세한 내용\(LIB 환경 변수에도 적용\)은 [VC\+\+ Directories, Projects, Options Dialog Box](http://msdn.microsoft.com/ko-kr/e027448b-c811-4c3d-8531-4325ad3f6e02)를 참조하십시오.  
  
 다음 예제는 꺾쇠 괄호를 사용한 파일 포함을 보여 줍니다.  
  
```  
#include <stdio.h>  
```  
  
 이 예제는 STDIO.H라는 파일의 내용을 소스 프로그램에 추가합니다.  꺾쇠 괄호를 사용하면 전처리기가 \/I 컴파일러 옵션으로 지정된 디렉터리를 검색한 후 STDIO.H의 INCLUDE 환경 변수에서 지정한 디렉터리를 검색합니다.  
  
 다음 예제는 따옴표로 묶인 형식을 사용한 파일 포함을 보여 줍니다.  
  
```  
#include "defs.h"  
```  
  
 이 예제는 DEFS.H에서 지정한 파일의 내용을 소스 프로그램에 추가합니다.  따옴표 기호는 전처리기가 먼저 상위 소스 파일이 포함된 디렉터리를 검색함을 의미합니다.  
  
 include 파일 중첩은 최대 10수준까지 할 수 있습니다.  중첩된 `#include`가 처리되면 전처리기가 include 파일을 원본 소스 파일에 삽입합니다.  
  
 **Microsoft 전용**  
  
 포함 가능한 소스 파일을 찾기 위해 전처리기는 먼저 \/I 컴파일러 옵션에서 지정한 디렉터리를 검색합니다.  \/I 옵션이 없거나 실패할 경우 전처리기는 INCLUDE 환경 변수를 사용하여 꺾쇠 괄호 안에 있는 모든 include 파일을 찾습니다.  INCLUDE 환경 변수 및 \/I 컴파일러 옵션에는 세미콜론\(;\)으로 구분된 여러 경로가 포함될 수 있습니다.  두 개 이상의 디렉터리가 \/I 옵션의 일부로 또는 INCLUDE 환경 변수 안에 있으면 전처리기는 디렉터리가 표시된 순서대로 검색합니다.  
  
 예를 들어 다음과 같은 명령은  
  
```  
CL /ID:\MSVC\INCLUDE MYPROG.C  
```  
  
 전처리기가 D:\\MSVC\\INCLUDE\\ 디렉터리에서 STDIO.H 등의 include 파일을 검색하도록 합니다.  다음의 명령 또한  
  
```  
SET INCLUDE=D:\MSVC\INCLUDE  
CL MYPROG.C  
```  
  
 동일한 결과를 산출합니다.  두 검색 집합이 모두 실패하면 치명적 컴파일러 오류가 생성됩니다.  
  
 콜론이 포함된 경로\(예: F:\\MSVC\\SPECIAL\\INCL\\TEST.H\)를 가진 include 파일에 대해 전체 파일 이름이 지정된 경우 전처리기는 해당 경로를 따라갑니다.  
  
 `#include` "`path-spec`"으로 지정된 include 파일의 경우 디렉터리 검색은 부모 파일의 디렉터리에서 시작하여 상위 부모 파일의 디렉터리로 진행됩니다.  즉, 처리 중인 `#include` 지시문이 포함된 소스 파일의 디렉터리를 기준으로 검색이 시작됩니다.  상위 부모 파일이 없고 파일이 검색되지 않은 경우 파일 이름이 꺾쇠 괄호로 묶여 있는 것처럼 검색이 진행됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)