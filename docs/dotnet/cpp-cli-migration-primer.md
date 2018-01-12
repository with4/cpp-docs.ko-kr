---
title: "C + + /CLI 마이그레이션 입문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- C++/CLI Version 2
- upgrading Visual C++ applications, Managed Extensions for C++ to Visual C++ 2005 syntax
- migration [C++], C++/CLI Version 2
- Managed Extensions for C++, upgrading syntax
- C++/CLI Version 2, managed extensions
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1dcbb3b54cbde323cda0856ca68b2281d669cb7b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccli-migration-primer"></a>C++/CLI 마이그레이션 입문
Visual c + + 프로그램에서 Managed Extensions for c + +로 이동 Visual c + +에 대 한 지침입니다. 참조에 대 한 변경 내용 구문 검사 목록 요약 [(NOTINBUILD) Managed Extensions for c + + 구문 업그레이드 검사 목록](http://msdn.microsoft.com/en-us/edbded88-7ef3-4757-bd9d-b8f48ac2aada)합니다.  
  
 C + + /cli는 동적 구성 요소 프로그래밍 패러다임 ISO c + + 표준 언어를 확장 합니다. 새 언어는 Managed Extensions를 통해 다양 한 향상 된 기능을 제공합니다. 이 섹션에서는 Visual c + + 여기서 해당 매핑이 존재 하 고 매핑이 존재 하는 이러한 구문에는 열거 된 목록을 통해 Managed Extensions for c + + 언어 기능 및 매핑을 제공 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [변경 사항 개요(C++/CLI)](../dotnet/outline-of-changes-cpp-cli.md)  
 에 대 한 변경 내용 목록이 일반 범주 아래에서 5 개를 제공 하는 빠른 참조를 간단히 설명 합니다.  
  
 [언어 키워드(C++/CLI)](../dotnet/language-keywords-cpp-cli.md)  
 두 개의 밑줄을 제거 하 고 및와 관련 키워드의 도입을 포함 하 여 언어 키워드에는 변경에 설명 합니다.  
  
 [관리 되는 형식 (C + + /cli CL)](../dotnet/managed-types-cpp-cl.md)  
 클래스, 배열 (매개 변수 배열 포함), 열거형, 및 등의 선언을 변경 되어이 보고가 구문 변경 된 선언의 CTS 공용 형식 시스템 ()-되었습니다.  
  
 [클래스 또는 인터페이스 내에서 멤버 선언(C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)  
 스칼라 속성, 인덱스 속성, 연산자, 대리자 및 이벤트 같은 클래스 멤버와 관련 된 변경 내용을 표시 합니다.  
  
 [값 형식 및 동작(C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 값 형식과 고정 및 내부 포인터의 새 제품군에 초점을 맞춥니다. 또한 암시적 boxing, 불변성 boxed 값 형식 및 값 클래스 내에서 기본 생성자에 대 한 지원이 제거 도입 등 중요 한 의미 체계가 변경 사항을 설명합니다.  
  
 [일반적인 언어 변경 사항(C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)  
 캐스트 표기법에 대 한 지원 등과 같은 세부 정보 의미 변경 문자열 리터럴 동작 및 ISO c + + 및 C + 간의 의미 체계에 대 한 변경 내용을 + CLI 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [혼합형된 (네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)   
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)