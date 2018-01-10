---
title: "CL 환경 변수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba01a980aa24a3ff695479edd08e88d9ea538dcc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cl-environment-variables"></a>CL 환경 변수

CL 도구는 다음과 같은 환경 변수를 사용합니다.

- CL 및 \_CL\_에 정의 합니다. CL 도구 옵션 및 명령줄 인수에 CL 환경 변수에 정의 된 인수 앞에 추가 하 고 옵션을 추가 및 인수에 정의 된 \_CL\_를 처리 하기 전에.

- INCLUDE. Visual C++ 설치의 \include 하위 디렉터리를 가리켜야 합니다.

- 사용 하 여 참조 메타 데이터 파일을 검색할 디렉터리를 지정 하는 LIBPATH [#using](../../preprocessor/hash-using-directive-cpp.md)합니다. LIBPATH에 대한 자세한 내용은 `#using`을 참조하세요.

CL을 설정할 수 있습니다 또는 \_CL\_ 다음 구문을 사용 하 여 환경 변수:

> CL 설정 = [[*옵션*]... [*파일*]...] [/ l *링크-opt* ...]  
> 설정 \_CL\_= [[*옵션*]... [*파일*]...] [/ l *링크-opt* ...]

CL에 대 한 인수에 대 한 자세한 내용은 및 \_CL\_ 환경 변수 참조 [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)합니다.

이러한 환경 변수를 사용하여 가장 자주 사용하는 파일 및 옵션을 정의하고 명령줄을 사용하여 특정 용도에 맞는 특정 파일 및 옵션을 정의할 수 있습니다. CL 및 \_CL\_ 환경 변수는 1024 자 (명령줄 입력된 제한)로 제한 합니다.

등호 기호(=)를 사용하는 기호를 정의할 때는 /D 옵션을 사용할 수 없습니다. 등호 기호에 대신 숫자 기호(#)를 사용할 수 있습니다. 이러한 방식으로 CL를 사용할 수 있습니다 또는 \_CL\_ 명시적 값으로 전처리기 상수를 정의 하는 환경 변수-예를 들어 `/DDEBUG#1` 정의 하려면 `DEBUG=1`합니다.

관련된 정보를 참조 하십시오. [환경 변수 설정](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)합니다.

## <a name="examples"></a>예제

다음은 CL 환경 변수 설정의 예입니다.

> CL = / Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE를 설정 합니다. OBJ

입력 하는 경우,이 환경 변수가 설정 되어 `CL INPUT.C` 명령은 명령줄에 효과적인 명령입니다.

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE 합니다. OBJ 입력입니다. C

다음 예제에서는 일반 CL 명령을 사용하여 소스 파일 FILE1.c 및 FILE2.c를 컴파일한 다음 개체 파일 FILE1.obj, FILE2.obj 및 FILE3.obj를 연결합니다.

> 집합 CL FILE1 = 합니다. C FILE2 합니다. C  
> 설정 \_CL\_FILE3 = 합니다. OBJ  
> CL  

이 예제는 다음 명령줄과 동일한 효과가 있습니다.

> CL FILE1 합니다. C FILE2 합니다. C FILE3 합니다. OBJ

## <a name="see-also"></a>참고 항목

[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
[컴파일러 옵션](../../build/reference/compiler-options.md)
