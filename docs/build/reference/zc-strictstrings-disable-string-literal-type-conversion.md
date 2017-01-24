---
title: "/Zc:strictStrings(문자열 리터럴 형식 변환 사용 안 함) | Microsoft Docs"
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
  - "/Zc:strictStrings"
  - "strictStrings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc 컴파일러 옵션(C++)"
  - "/Zc:strictStrings"
  - "strictStrings"
  - "Zc 컴파일러 옵션(C++)"
  - "-Zc 컴파일러 옵션(C++)"
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:strictStrings(문자열 리터럴 형식 변환 사용 안 함)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정한 경우 컴파일러에는 문자열 리터럴을 사용하여 초기화한 포인터에 대한 엄격한 `const` 한정 규칙이 필요합니다.  
  
## 구문  
  
```  
/Zc:strictStrings[-]  
```  
  
## 설명  
 **\/Zc:strictStrings**를 지정하면 컴파일러에서는 선언에 따라 문자열 리터럴에 대한 표준 C\+\+ `const` 한정을 '`const` `char` 배열' 또는 '`const` `wchar_t` 배열'의 형식으로 강제합니다.  문자열 리터럴은 변경 불가능하고 문자열 리터럴 중 하나의 내용을 수정하려고 하면 런타임에 액세스 위반 오류가 발생합니다.  문자열 포인터를 `const`로 선언하여 문자열 리터럴을 사용하여 초기화하거나 명시적 `const_cast`를 사용하여 비`const` 포인터를 초기화해야 합니다.  또는 기본적으로 **\/Zc:strictStrings\-**를 지정한 경우 컴파일러에서는 문자열 리터럴을 사용하여 초기화된 문자열 포인터에 대해 표준 C\+\+ `const` 한정을 적용하지 않습니다.  
  
 잘못된 코드의 컴파일을 방지하려면 **\/Zc:strictStrings** 옵션을 사용합니다.  다음 예제에서는 간단한 선언 오류가 런타임에 충돌을 어떻게 발생시키는지 보여줍니다.  
  
```cpp  
// strictStrings_off.cpp  
// compile by using: cl /W4 strictStrings_off.cpp  
int main() {  
   wchar_t* str = L"hello";  
   str[2] = L'a'; // run-time error: access violation  
}  
```  
  
 **\/Zc:strictStrings**를 사용하면 `str` 선언 시 동일한 코드가 오류를 보고합니다.  
  
```cpp  
// strictStrings_on.cpp  
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp  
int main() {  
   wchar_t* str = L"hello"; // error: Conversion from string literal   
   // loses const qualifier  
   str[2] = L'a';   
}  
```  
  
 `auto`를 사용하여 문자열 포인터를 선언하면 컴파일러에서는 올바른 `const` 포인터 형식 선언을 만듭니다.  `const` 포인터의 내용을 수정하려는 시도는 컴파일러에서 오류로 보고합니다.  
  
> [!NOTE]
>  [!INCLUDE[cpp_dev12_long](../../build/reference/includes/cpp_dev12_long_md.md)]의 표준 C\+\+ 라이브러리는 디버그 빌드에서 **\/Zc:strictStrings** 컴파일러 옵션을 지원하지 않습니다.  빌드 출력에 여러 [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) 오류가 있는 경우 이것이 원인일 수 있습니다.  
  
 Visual C\+\+의 규칙과 관련된 문제에 대한 자세한 내용은 [비표준 동작](../../cpp/nonstandard-behavior.md)을 참조하세요.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  `/Zc:strictStrings`을 포함하도록 **추가 옵션** 속성을 수정한 다음 **확인**을 선택합니다.  
  
## 참고 항목  
 [\/Zc\(규칙\)](../../build/reference/zc-conformance.md)