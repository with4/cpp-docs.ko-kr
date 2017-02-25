---
title: "프로세스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Process"
  - "process_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], 프로세스"
  - "process __declspec 키워드"
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# 프로세스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로세스의 모든 응용 프로그램 도메인에서 공유되는 특정 전역 변수, 정적 멤버 변수 또는 정적 지역 변수의 단일 복사본이 관리되는 응용 프로그램 프로세스에 있어야 함을 지정합니다.  **\/clr:pure**에서는 전역 및 정적 변수가 기본적으로 응용 프로그램 도메인별이기 때문에 이는 주로 **\/clr:pure**로 컴파일할 때 사용됩니다.  **\/clr**로 컴파일하는 경우 전역 및 정적 변수는 기본적으로 프로세스별입니다. 그러므로 `__declspec(process)`를 사용할 필요가 없습니다.  
  
 전역 변수, 정적 멤버 변수 또는 네이티브 형식의 정적 지역 변수만 `__declspec(process)`로 표시할 수 있습니다.  
  
 **\/clr:pure**로 컴파일하는 경우 프로세스별로 표시된 변수도 `const`로 선언되어야 합니다.  이렇게 하면 프로세스별 변수가 한 응용 프로그램 도메인에서 변경되지 않아 다른 응용 프로그램 도메인에서 예기치 않은 결과가 발생합니다.  `__declspec(process)`는 주로 **\/clr:pure**에서 전역 변수, 정적 멤버 변수 또는 정적 지역 변수의 컴파일 타임 초기화를 가능하게 만드는 데 사용됩니다.  
  
 `process` 는 [\/clr](../build/reference/clr-common-language-runtime-compilation.md) 또는 **\/clr:pure**로 컴파일하는 경우에만 유효하고 **\/clr:safe**로 컴파일하는 경우에는 유효하지 않습니다.  
  
 각 응용 프로그램 도메인에 전역 변수의 자체 복사본을 두려면 [appdomain](../cpp/appdomain.md)을 사용하십시오.  
  
 자세한 내용은 [응용 프로그램 도메인 및 Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md)를 참조하십시오.  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)