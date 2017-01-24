---
title: "__thiscall | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__thiscall"
  - "__thiscall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__thiscall 키워드[C++]"
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __thiscall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 `__thiscall` 호출 컨벤션은 멤버 함수에서 사용되고 가변 인수를 사용하지 않는 C\+\+ 멤버가 사용하는 디폴트 호출 컨벤션입니다.  `__thiscall` 아래에 호출 수신자가 스택을 정리하여 `vararg` 함수를 이용할 수 없습니다.  인수는 x86 아키텍처에서 스택이 아닌 레지스터 ECX를 통해 전달되는 `this` 포인터를 사용하여 오른쪽에서 왼쪽으로 스택에 푸시됩니다.  
  
 `__thiscall` 사용하는 이유 중 하나는 그 멤버 함수가 기본적으로 `__clrcall` 사용하는 클래스 안에 있습니다.  이 경우 `__thiscall`을 사용하여 네이티브 코드에서 개별 멤버 함수를 호출할 수 있습니다.  
  
 [\/clr:pure](../build/reference/clr-common-language-runtime-compilation.md)로 컴파일하는 경우 다른 함수가 지정되지 않는 한 모든 함수 및 함수 포인터는 `__clrcall`입니다.  
  
 Visual C\+\+ 2005 이전의 릴리스의 경우 `thiscall`이 키워드가 아니었기 때문에 프로그램에 thiscall 호출 규칙을 명시적으로 지정할 수 없었습니다.  
  
 `vararg` 멤버 함수는 `__cdecl` 호출 규칙을 사용합니다.  모든 함수 인수가 스택에 푸시되고 `this` 포인터가 스택에 마지막으로 배치됩니다.  
  
 이 호출 규칙이 C\+\+에만 적용되기 때문에 C 이름 데코레이션 구성표가 없습니다.  
  
 ARM 및 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 시스템에서는 컴파일러가 `__thiscall` 을 수락할지 무시할지 결정합니다.  
  
 비정적 클래스 함수의 경우 함수가 아웃오브 라인으로 정의되면 호출 규칙 한정자를 아웃오브 라인 정의에서 지정하지 않아도 됩니다.  즉, 클래스 비정적 멤버 메서드의 경우 선언하는 동안 지정된 호출 규칙이 정의 시 가정됩니다.  
  
## 예제  
  
```  
// thiscall_cc.cpp  
// compile with: /c /clr:oldSyntax  
struct CMyClass {  
   void __thiscall mymethod();  
   void __clrcall mymethod2();  
};  
```  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)