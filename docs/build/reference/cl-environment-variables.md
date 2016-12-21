---
title: "CL 환경 변수 | Microsoft Docs"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 환경 변수"
  - "환경 변수, CL 컴파일러"
  - "INCLUDE 환경 변수"
  - "LIBPATH 환경 변수"
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CL 환경 변수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL 도구는 다음과 같은 환경 변수를 사용합니다.  
  
-   CL 및 \_CL\_\(정의된 경우\).  CL 도구는 처리 전에 CL 환경 변수에 정의된 옵션 및 인수를 명령줄 인수 앞에 추가하고 \_CL\_에 정의된 옵션 및 인수를 뒤에 추가합니다.  
  
-   INCLUDE. Visual C\+\+ 설치의 \\include 하위 디렉터리를 가리켜야 합니다.  
  
-   LIBPATH. [\#using](../../preprocessor/hash-using-directive-cpp.md)을 사용하여 참조된 메타데이터 파일을 검색할 디렉터리를 지정합니다.  LIBPATH에 대한 자세한 내용은 `#using`을 참조하세요.  
  
 다음 구문을 사용하여CL 또는 \_CL\_ 환경 변수를 설정할 수 있습니다.  
  
```  
SET CL=[ [option] ... [file] ...] [/link link-opt ...]  
SET _CL_=[ [option] ... [file] ...] [/link link-opt ...]  
```  
  
 CL 및 \_CL\_ 환경 변수의 인수에 대한 세부 정보는 [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)을 참조하세요.  
  
 이러한 환경 변수를 사용하여 가장 자주 사용하는 파일 및 옵션을 정의하고 명령줄을 사용하여 특정 용도에 맞는 특정 파일 및 옵션을 정의할 수 있습니다.  CL 및 \_CL\_ 환경 변수는 1024자\(명령줄 입력 제한\)로 제한됩니다.  
  
 등호 기호\(\=\)를 사용하는 기호를 정의할 때는 \/D 옵션을 사용할 수 없습니다.  등호 기호에 대신 숫자 기호\(\#\)를 사용할 수 있습니다.  이런 식으로 CL 또는 \_CL\_ 환경 변수를 사용하여 명시적 값으로 전처리기 상수를 정의할 수 있습니다. 예를 들어 `DDEBUG #1`로 `DEBUG=1`을 정의할 수 있습니다.  
  
 관련된 정보는 [환경 변수 설정](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요.  
  
## 예  
 다음은 CL 환경 변수를 설정하는 예입니다.  
  
```  
SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ  
```  
  
 이 환경 변수가 설정된 경우 명령줄에 `CL INPUT.C`를 입력하면 명령이 적용됩니다.  
  
```  
CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C  
```  
  
 다음 예제에서는 일반 CL 명령을 사용하여 소스 파일 FILE1.c 및 FILE2.c를 컴파일한 다음 개체 파일 FILE1.obj, FILE2.obj 및 FILE3.obj를 연결합니다.  
  
```  
SET CL=FILE1.C FILE2.C  
SET _CL_=FILE3.OBJ  
CL  
  
```  
  
 이 예제는 다음 명령줄과 동일한 효과가 있습니다.  
  
```  
CL FILE1.C FILE2.C FILE3.OBJ  
```  
  
## 참고 항목  
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)