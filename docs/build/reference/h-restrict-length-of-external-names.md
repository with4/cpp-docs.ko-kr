---
title: "/H(외부 이름 길이 제한) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/h"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/H 컴파일러 옵션[C++]"
  - "외부 이름"
  - "H 컴파일러 옵션[C++]"
  - "-H 컴파일러 옵션[C++]"
  - "공개 이름 길이"
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /H(외부 이름 길이 제한)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

외부 이름의 길이를 제한합니다.  
  
## 구문  
  
```  
/Hnumber  
```  
  
## 인수  
 `number`  
 프로그램에서 사용할 수 있는 외부 이름의 최대 길이를 지정합니다.  
  
## 설명  
 기본적으로 외부 공개 이름의 길이는 2,047자입니다.  C 및 C\+\+ 프로그램에서도 마찬가지입니다.  **\/H**를 사용하면 식별자의 가능한 최대 길이가 줄어들 수 있습니다.  **\/H**와 `number` 사이에는 공백을 넣어도 되고 넣지 않아도 됩니다.  
  
 프로그램에 `number`보다 긴 외부 이름이 있으면 나머지 문자는 무시됩니다.  **\/H**를 사용하지 않고 프로그램을 컴파일하거나 식별자의 문자 수가 2,047보다 많으면 컴파일러에서 [심각한 오류 C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md)가 발생합니다.  
  
 모든 컴파일러가 생성하는 선행 밑줄\(\_\) 또는 @ 기호도 길이 제한에 포함됩니다.  이러한 문자는 식별자의 일부분이며 중요한 의미를 갖습니다.  
  
-   컴파일러는 `__cdecl`\(기본값\)과 `__stdcall` 호출 규칙으로 수정한 이름에는 선행 밑줄\(\_\)을 추가하고, `__fastcall` 호출 규칙으로 수정한 이름에는 선행 @ 기호를 추가합니다.  
  
-   컴파일러는 `__fastcall` 및 `__stdcall` 호출 규칙으로 수정한 이름에는 인수 크기 정보를 추가하고, C\+\+ 이름에는 형식 정보를 추가합니다.  
  
 **\/H**는 다음과 같은 경우에 유용하게 사용할 수 있습니다.  
  
-   언어를 혼용하여 사용하거나 이식 가능한 프로그램을 만드는 경우.  
  
-   외부 식별자의 길이를 제한하는 도구를 사용하는 경우.  
  
-   디버그 빌드에서 기호가 사용하는 공간의 크기를 제한하려는 경우  
  
 다음 예제는 식별자 길이가 너무 많이 제한된 경우 **\/H**를 사용하면 실제로 오류가 어떻게 나타날 수 있는지를 보여 줍니다.  
  
```  
// compiler_option_H.cpp  
// compile with: /H5  
// processor: x86  
// LNK2005 expected  
void func1(void);  
void func2(void);  
  
int main() { func1(); }  
  
void func1(void) {}  
void func2(void) {}  
```  
  
 또한 **\/H** 옵션을 사용할 때에는 미리 정의된 컴파일러 식별자가 있으므로 주의해야 합니다.  식별자의 최대 길이가 너무 작으면 특정 라이브러리 함수 호출 뿐만 아니라 미리 정의된 특정 식별자가 확인되지 않을 수 있습니다.  예를 들어, 컴파일 타임에 `printf` 함수가 사용되고 **\/H5** 옵션이 지정되어 있으면, `printf`를 참조하기 위해 **\_prin** 기호가 만들어지며 이 기호는 라이브러리에 나타나지 않습니다.  
  
 **\/H**는 [\/GL\(전체 프로그램 최적화\)](../../build/reference/gl-whole-program-optimization.md)과 함께 사용할 수 없습니다.  
  
 **\/H**가 사용되지 않습니다. 최대 길이 제한값이 증가했으므로 **\/H**가 이제는 필요하지 않습니다.  자세한 내용은 [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)