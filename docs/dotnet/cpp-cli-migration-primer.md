---
title: "C++/CLI 마이그레이션 입문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++/CLI 버전 2"
  - "C++/CLI 버전 2, managed extensions"
  - "Managed Extensions for C++, 구문 업그레이드"
  - "마이그레이션[C++], C++/CLI 버전 2"
  - "Visual C++ 응용 프로그램 업그레이드, Managed Extensions for C++에서 Visual C++ 2005 구문으로"
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++/CLI 마이그레이션 입문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 단원에서는 Visual C\+\+ 프로그램을 Managed Extensions for C\+\+에서 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]로 이동하는 방법에 대해 설명합니다.  변경된 구문을 요약한 검사 목록은 [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/ko-kr/edbded88-7ef3-4757-bd9d-b8f48ac2aada)을 참조하십시오.  
  
 C\+\+\/CLI는 ISO\-C\+\+ 표준 언어에 대한 동적 구성 요소 프로그래밍 패러다임을 확장합니다.  새로운 언어를 통해 Managed Extensions에 대한 몇 가지 중요한 개선 사항이 제공됩니다.  이 단원에서는 Managed Extensions for C\+\+ 언어 기능을 나열한 목록을 제공하고 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서 각 기능이 어떠한 위치에서 어떻게 매핑되는지 설명합니다. 매핑되는 항목이 없는 경우 해당 구문에 대해서도 설명합니다.  
  
## 단원 내용  
 [변경 사항 개요\(C\+\+\/CLI\)](../dotnet/outline-of-changes-cpp-cli.md)  
 다섯 가지 일반적인 범주에서 변경된 사항에 대한 목록과 함께 빠른 참조에 대한 고급 수준의 개요를 제공합니다.  
  
 [언어 키워드\(C\+\+\/CLI\)](../dotnet/language-keywords-cpp-cli.md)  
 두 개의 밑줄 제거 및 컨텍스트 키워드와 공백이 포함된 키워드 도입 등의 언어 키워드 관련 변경 내용에 대해 설명합니다.  
  
 [관리되는 형식\(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)  
 CTS\(공용 형식 시스템\)에서 변경된 선언 구문에 대해 설명합니다. 여기에는 클래스, 배열\(매개 변수 배열 포함\), 열거형 등의 선언에서 변경된 내용이 포함됩니다.  
  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)  
 스칼라 속성, 인덱스 속성, 연산자, 대리자, 이벤트 등과 같은 클래스 멤버와 관련된 변경 사항에 대해 설명합니다.  
  
 [값 형식 및 동작\(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 값 형식과 내부 포인터 및 고정 포인터의 새로운 패밀리에 대해 중점적으로 설명합니다.  암시적 boxing 도입, boxed 값 형식의 불변성, 값 클래스 내에서 기본 생성자의 지원 제거 등과 같은 몇 가지 중요한 의미 변경 사항에 대해서도 설명합니다.  
  
 [일반적인 언어 변경 사항](../dotnet/general-language-changes-cpp-cli.md)  
 ISO\-C\+\+ 및 C\+\+\/CLI 사이의 의미에서 변경된 내용, 문자열 리터럴 동작, 캐스트 표기법에 대한 지원 등과 같은 의미 변경 사항에 대해 자세하게 설명합니다.  
  
## 참고 항목  
 [혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)