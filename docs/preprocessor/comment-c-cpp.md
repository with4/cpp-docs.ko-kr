---
title: "주석 (C/c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.comment
- comment_CPP
dev_langs:
- C++
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragmas, comment
- comment pragma
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1062923f50470a2238af21676c4137fac241905
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="comment-cc"></a>C 주석 (C/C++)
주석 기록을 개체 파일 또는 실행 파일에 배치합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma comment( comment-type [,"commentstring"] )  
```  
  
## <a name="remarks"></a>설명  
 *주석 형식* 주석 기록 형식을 지정 하는 하나 아래에서 설명 하는 미리 정의 된 식별자입니다. 선택적 `commentstring`은 일부 주석 형식에 추가 정보를 제공하는 문자열 리터럴입니다. 때문에 `commentstring` 은 문자열 리터럴, 이스케이프 문자를 포함 된 큰 따옴표와 관련 하 여 문자열 리터럴에 대 한 모든 규칙을 따르는 (**"**), 및 연결 합니다.  
  
 **compiler**  
 컴파일러의 이름 및 버전 이름을 개체 파일에 배치합니다. 이 주석 기록은 링커에 의해 무시됩니다. 이 기록 형식에 `commentstring` 매개 변수를 제공한 경우 컴파일러에서 경고를 생성합니다.  
  
 **exestr**  
 `commentstring`을 개체 파일에 배치합니다. 이 문자열은 링크 타임에 실행 파일에 배치됩니다. 이 문자열은 실행 파일이 로드될 때 메모리에 로드되지 않지만, 파일 내에 인쇄 가능한 문자열을 찾는 프로그램에서는 발견될 수 있습니다. 이 주석 기록 형식의 용도는 실행 파일의 버전 번호 또는 유사 정보를 포함하는 것입니다.  
  
 `exestr`은 사용되지 않으며 추후 버전에서 제거됩니다. 따라서 주석 기록은 링커에서 처리되지 않습니다.  
  
 **lib**  
 라이브러리 검색 기록을 개체 파일에 배치합니다. 이러한 주석 형식은 링커가 검색할 라이브러리의 이름(그리고 가능하면 경로까지)을 포함하는 `commentstring` 매개 변수를 수반해야 합니다. 라이브러리 이름은 개체 파일에 기본 라이브러리 검색 기록을 따릅니다. 링커 경우는 라이브러리에 지정 되지 않은 명령줄에서 라는 했습니다 처럼이 라이브러리에 대 한 검색 [/nodefaultlib](../build/reference/nodefaultlib-ignore-libraries.md)합니다. 여러 라이브러리 검색 기록을 같은 소스 파일에 배치할 수 있으며 각 기록은 소스 파일과 동일한 순서로 개체 파일에 표시됩니다.  
  
 기본 라이브러리 및 추가 된 라이브러리의 순서가 중요 한 경우 사용 하 여 컴파일하는 [/Zl](../build/reference/zl-omit-default-library-name.md) 스위치 개체 모듈에 배치 되지 않게 기본 라이브러리 이름을 수 없게 됩니다. 그런 다음 두 번째 주석 pragma를 사용하여 추가된 라이브러리 다음에 기본 라이브러리의 이름을 삽입할 수 있습니다. pragma를 사용하여 나열된 라이브러리는 소스 코드와 동일한 순서로 개체 모듈에 표시됩니다.  
  
 **linker**  
 위치는 [링커 옵션](../build/reference/linker-options.md) 개체 파일에 있습니다. 이 주석 형식을 이용하여 명령줄에 주석을 전달하거나 개발 환경에 지정하는 대신 링커 옵션을 지정할 수 있습니다. 예를 들어, /include 옵션을 지정하면 기호를 포함하도록 할 수 있습니다.  
  
```  
#pragma comment(linker, "/include:__mySymbol")  
```  
  
 다음만 (*주석 형식*) 링커 옵션을 링커 식별자로 전달할 수 없습니다.  
  
-   [/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)  
  
-   [/EXPORT](../build/reference/export-exports-a-function.md)  
  
-   [/INCLUDE](../build/reference/include-force-symbol-references.md)  
  
-   [/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)  
  
-   [/MERGE](../build/reference/merge-combine-sections.md)  
  
-   [/SECTION](../build/reference/section-specify-section-attributes.md)  
  
 **user**  
 일반 주석을 개체 파일에 배치합니다. `commentstring` 매개 변수에는 주석 텍스트가 들어 있습니다. 이 주석 기록은 링커에 의해 무시됩니다.  
  
 다음 pragma를 사용하면 링커가 연결하는 동안 EMAPI.LIB 라이브러리를 검색할 수 있습니다. 링커는 먼저 현재 작업 경로에서 검색한 다음 LIB 환경 변수에 지정된 경로에서 검색합니다.  
  
```  
#pragma comment( lib, "emapi" )  
```  
  
 다음 pragma는 컴파일러가 컴파일러의 이름과 버전 번호를 개체 파일에 배치하도록 합니다.  
  
```  
#pragma comment( compiler )  
```  
  
> [!NOTE]
>  `commentstring` 매개 변수를 사용하는 주석의 경우 매크로가 문자열 리터럴로 확장되면 문자열 리터럴이 사용되는 모든 위치에 매크로를 사용할 수 있습니다. 문자열 리터럴에 확장되는 문자열 리터럴 및 매크로의 조합을 연결할 수도 있습니다. 예를 들어, 다음 문을 사용할 수 있습니다.  
  
```  
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )   
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)