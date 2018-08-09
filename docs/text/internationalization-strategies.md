---
title: 국제화 전략 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a3b8a47e70efa3268ae9b36eda311d267be2ded
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018931"
---
# <a name="internationalization-strategies"></a>국제화 전략
대상 운영 체제 및 시장에 따라 여러 국제화 전략 해야합니다.  
  
-   응용 프로그램에서 유니코드를 사용 합니다.  
  
     유니코드 관련 기능을 사용 하 고 모든 문자는 너비가 16 비트 (특수 목적을 위해 프로그램의 일부에서 ANSI 문자를 사용할 수 있습니다). C 런타임 라이브러리 유니코드 전용 프로그래밍에 대 한 함수, 매크로 및 데이터 형식을 제공합니다. MFC는 유니코드를 완벽 하 게 지원 합니다.  
  
-   응용 프로그램이 MBCS를 사용 하며 모든 Win32 플랫폼에서 실행할 수 있습니다.  
  
     MBCS 관련 기능을 사용 합니다. 문자열에는 싱글바이트 문자, 더블 바이트 문자 또는 둘 다 포함 될 수 있습니다. C 런타임 라이브러리 MBCS 전용 프로그래밍에 대 한 함수, 매크로 및 데이터 형식을 제공합니다. MFC는 완벽 하 게 MBCS 지원 합니다.  
  
-   전체 이식성에 대 한 응용 프로그램에 대 한 소스 코드를 작성-기호를 사용 하 여 다시 컴파일하여 `_UNICODE` 기호 또는 `_MBCS` 정의 버전을 사용 하 여 생성할 수 있습니다. 자세한 내용은 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)합니다.  
  
     완전히 이식 가능한 C 런타임 함수, 매크로 및 데이터 형식을 사용할 수 있습니다. MFC의 유연성을 지 원하는 이러한 전략 중 하나입니다.  
  
 이러한 항목의 나머지 부분에서는 MBCS 또는 유니코드로 빌드할 수 있는 완전히 이식 가능한 코드 작성에 집중 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [유니코드 및 MBCS](../text/unicode-and-mbcs.md)   
 [로캘 및 코드 페이지](../text/locales-and-code-pages.md)