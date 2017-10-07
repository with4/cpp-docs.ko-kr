---
title: "프로세스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d4f2500adaaa7941444b22d7ce548370fc370533
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="process"></a>process
프로세스의 모든 응용 프로그램 도메인에서 공유되는 특정 전역 변수, 정적 멤버 변수 또는 정적 지역 변수의 단일 복사본이 관리되는 응용 프로그램 프로세스에 있어야 함을 지정합니다. 이 방법은 주로 사용 하 여 컴파일할 때 사용 되는 **/clr: pure**때문에에서 **/clr: 순수** 전역 및 정적 변수는 기본적으로 응용 프로그램 도메인, 합니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다. 로 컴파일할 때 **/clr**, 전역 및 정적 변수는 기본적으로 프로세스별 (사용할 필요가 없습니다 `__declspec(process)`합니다.  
  
 전역 변수, 정적 멤버 변수 또는 네이티브 형식의 정적 지역 변수만 `__declspec(process)`로 표시할 수 있습니다.  
  
 로 컴파일할 때 **/clr: pure**,으로 프로세스 별로 표시 된 변수를 선언 해야 `const`합니다. 이렇게 하면 프로세스별 변수가 한 응용 프로그램 도메인에서 변경되지 않아 다른 응용 프로그램 도메인에서 예기치 않은 결과가 발생합니다. 주로 사용 `__declspec(process)` 전역 변수, 정적 멤버 변수 또는 정적 지역 변수의 컴파일 타임 초기화를 사용 하도록 설정 하는 것 **/clr: pure**합니다.  
  
 `process`로 컴파일할 때만 유효 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 또는 **/clr: pure** 로 컴파일할 때 유효 하지 않습니다 **/clr: safe**합니다.  
  
 전역 변수의 자체 복사본을 각 응용 프로그램 도메인 사용 [appdomain](../cpp/appdomain.md)합니다.  
  
 참조 [응용 프로그램 도메인 및 Visual c + +](../dotnet/application-domains-and-visual-cpp.md) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)
