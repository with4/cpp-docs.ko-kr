---
title: "main: 프로그램 시작 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc.main.startup"
  - "_tmain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tmain 함수"
  - "진입점, 프로그램"
  - "main 함수, 프로그램 시작"
  - "프로그램 시작[C++]"
  - "시작 코드, main 함수"
  - "wmain 함수"
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# main: 프로그램 시작
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`main`이라는 특수 함수는 모든 C 및 [!INCLUDE[TLA#tla_cpp](../cpp/includes/tlasharptla_cpp_md.md)] 프로그램의 실행이 시작되는 지점입니다.  [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)] 프로그래밍 모델을 따르는 코드를 작성하는 경우 `main`의 와이드 문자 버전인 `wmain`을 사용할 수 있습니다.  
  
 `main` 함수는 컴파일러에서 미리 정의되지 않으며,  프로그램 텍스트에서 제공되어야 합니다.  
  
 `main`의 선언 구문은 다음과 같습니다.  
  
```  
int main();  
```  
  
 또는 필요에 따라 다음과 같은 선언 구문을 사용할 수 있습니다.  
  
```  
int main(int argc, char *argv[], char *envp[]);  
```  
  
## Microsoft 전용  
 `wmain`의 선언 구문은 다음과 같습니다.  
  
```  
int wmain( );  
```  
  
 또는 필요에 따라 다음과 같은 선언 구문을 사용할 수 있습니다.  
  
```  
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 TCHAR.h에 정의된 `_tmain`을 사용할 수도 있습니다.  `_tmain`은 \_UNICODE가 정의되지 않은 한 `main`으로 확인됩니다.  \_UNICODE가 정의된 경우에는 `_tmain`이 `wmain`으로 확인됩니다.  
  
 또는 `main` 및 `wmain` 함수가 `void`\(반환 값 없음\)를 반환하는 것으로 선언될 수 있습니다.  `void`를 반환하는 것으로 `main` 또는 `wmain`을 선언하는 경우 [return](../cpp/return-statement-in-program-termination-cpp.md) 문을 사용하여 부모 프로세스나 운영 체제에 종료 코드를 반환할 수 없습니다.  `main` 또는 `wmain`이 `void`를 반환하는 것으로 선언된 경우 종료 코드를 반환하려면 [exit](../cpp/exit-function.md) 함수를 사용해야 합니다.  
  
## Microsoft 전용 종료  
 `argc` 및 `argv`의 형식은 언어에서 정의됩니다.  `argc`, `argv` 및 `envp`라는 이름이 일반적으로 사용되지만 컴파일러에서 필요하지는 않습니다.  자세한 내용과 예제는 [인수 정의](../cpp/argument-definitions.md)를 참조하십시오.  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [main 대신 wmain 사용](../cpp/using-wmain-instead-of-main.md)   
 [main 함수 제한](../cpp/main-function-restrictions.md)