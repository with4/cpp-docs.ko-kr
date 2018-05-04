---
title: 프로세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aa1ba2676ebbd04d1fc1a59d210d69efeab6658
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="process"></a>process
프로세스의 모든 응용 프로그램 도메인에서 공유되는 특정 전역 변수, 정적 멤버 변수 또는 정적 지역 변수의 단일 복사본이 관리되는 응용 프로그램 프로세스에 있어야 함을 지정합니다. 이 사용 하 여 컴파일할 때 사용 되는 주로 되었습니다 **/clr: pure**는 이제 사용 되지 않는 및 이후 버전의 컴파일러에서 제거 됩니다. 로 컴파일할 때 **/clr**, 전역 및 정적 변수는 기본적으로 프로세스별 (사용할 필요가 없습니다 `__declspec(process)`합니다.  
  
 전역 변수, 정적 멤버 변수 또는 네이티브 형식의 정적 지역 변수만 `__declspec(process)`로 표시할 수 있습니다.  
  
  
 `process` 로 컴파일할 때만 유효 [/clr](../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
 전역 변수의 자체 복사본을 각 응용 프로그램 도메인 사용 [appdomain](../cpp/appdomain.md)합니다.  
  
 참조 [응용 프로그램 도메인 및 Visual c + +](../dotnet/application-domains-and-visual-cpp.md) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)