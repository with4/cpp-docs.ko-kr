---
title: "/D(전처리기 정의) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.PreprocessorDefinitions"
  - "VC.Project.VCCLCompilerTool.PreprocessorDefinitions"
  - "/d"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/D 컴파일러 옵션[C++]"
  - "상수, 정의"
  - "D 컴파일러 옵션[C++]"
  - "-D 컴파일러 옵션[C++]"
  - "매크로, 컴파일"
  - "전처리기 정의 기호"
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# /D(전처리기 정의)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

소스 파일에 대한 전처리 기호를 정의합니다.  
  
## 구문  
  
```  
/Dname[= | # [{string | number}] ]  
```  
  
## 설명  
 이 기호를 `#if` 또는 `#ifdef`와 함께 사용하여 조건에 따라 소스 코드를 컴파일할 수 있습니다.  기호 정의는 코드에서 기호를 다시 정의하거나 `#undef` 지시문을 사용하여 코드에서 기호 정의를 해제할 때까지 유효합니다.  
  
 **\/D**는 명령줄 및 `#define`의 **\/D** 스트립 따옴표가 효과를 유지한다는 점을 제외하고 소스 코드 파일의 시작 부분에 있는 `#define` 지시문과 같은 효과를 갖고 있습니다.  
  
 기호와 관련된 값은 기본적으로 1입니다.  예를 들어 **\/D**`name`은 **\/D**`name`**\=1**과 같습니다.  이 문서 끝 부분의 예제에서 **TEST**의 정의는 `1`을 인쇄하는 것으로 나와 있습니다.  
  
 **\/D** `name` **\=**을 사용하여 컴파일하면 기호와 연결된 값이 만들어지지 않습니다.  기호를 사용해 조건에 따라 코드를 컴파일할 수 있지만 그렇지 않은 경우 기호가 어떤 값으로도 계산되지 않습니다.  이 예제에서는 **\/DTEST\=**를 사용하여 컴파일하면 오류가 발생합니다.  이 동작은 값을 사용하거나 사용하지 않을 때에도 `#define`을 사용할 때의 동작과 비슷합니다.  
  
 이 명령은 TEST.c에서 DEBUG 기호를 정의합니다.  
  
 **CL \/DDEBUG  TEST.C**  
  
 이 명령은 TEST.c에 있는 모든 `__far` 키워드를 제거합니다.  
  
 **CL \/D\_\_far\=  TEST.C**  
  
 **CL** 환경 변수는 등호를 포함하는 문자열에 설정할 수 없습니다.  **\/D**와 **CL** 환경 변수를 함께 사용하려면 다음과 같이 등호 대신에 숫자 기호를 지정해야 합니다.  
  
```  
SET CL=/DTEST#0  
```  
  
 명령 프롬프트에서 전처리 기호를 정의하면 컴파일러 구문 분석 규칙과 셸 구문 분석 규칙을 모두 수행하는 것이 좋습니다.  예를 들어 프로그램에서 백분율 기호 전처리 기호\(%\)를 정의하려면 명령 프롬프트에서 두 개의 백분율 기호 문자\(%%\)를 지정합니다. 문자를 하나만 지정하면 구문 분석 오류가 내보내집니다.  
  
```  
CL /DTEST=%% TEST.C  
```  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  왼쪽 창에서 **구성 속성**, **C\/C\+\+**, **전처리기**를 선택합니다.  
  
3.  오른쪽 창에 있는 **전처리기 정의** 속성의 오른쪽 열에서 드롭다운 메뉴를 열고 **편집**을 선택합니다.  
  
4.  **전처리기 정의** 대화 상자에서 하나 이상의 정의를 한 줄에 하나씩 추가, 수정 또는 삭제합니다.  **확인**을 선택하여 변경 내용을 저장합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>를 참조하십시오.  
  
## 예제  
  
```  
// cpp_D_compiler_option.cpp  
// compile with: /DTEST  
#include <stdio.h>  
  
int main( )  
{  
    #ifdef TEST  
        printf_s("TEST defined %d\n", TEST);  
    #else  
        printf_s("TEST not defined\n");  
    #endif  
}  
```  
  
  **TEST 정의됨 1**   
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [\/U, \/u\(기호 정의 해제\)](../../build/reference/u-u-undefine-symbols.md)   
 [\#undef 지시문](../../preprocessor/hash-undef-directive-c-cpp.md)   
 [\#define 지시문](../../preprocessor/hash-define-directive-c-cpp.md)