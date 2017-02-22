---
title: "유니코드 및 MBCS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MBCS[C++], 유니코드"
  - "MFC[C++], 문자 집합"
  - "문자 집합[C++], 멀티바이트"
  - "런타임 라이브러리[C++], 언어 이식성"
  - "문자 집합[C++], 유니코드"
  - "유니코드[C++], MFC 및 C 런타임 함수"
  - "멀티바이트 문자[C++]"
  - "런타임[C++], 언어 이식성"
ms.assetid: 677baec6-71b4-4579-94df-64f18bc117c4
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# 유니코드 및 MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC\(Microsoft Foundation Class\) 라이브러리, Visual C\+\+용 C 런타임 라이브러리 및 Visual C\+\+ 개발 환경에서 국가별 프로그래밍이 지원됩니다.  그 내용은 다음과 같습니다.  
  
-   Windows 2000\(이전의 Windows NT\)에서 유니코드 표준 지원  유니코드는 현재의 표준이며 어디에서든 항상 사용가능해야 합니다.  
  
     유니코드는 모든 언어에 대한 충분한 인코딩을 제공하는 16비트 문자 인코딩입니다.  모든 ASCII 문자는 와이드 문자로서 유니코드에 포함됩니다.  
  
    > [!NOTE]
    >  유니코드 표준은 Windows 95, Windows 98 또는 Windows Millennium Edition에서 지원되지 않습니다.  
  
-   모든 플랫폼에서 DBCS\(더블바이트 문자 집합\)로 불리는 MBCS\(멀티바이트 문자 집합\) 형식 지원  
  
     DBCS 문자는 1바이트나 2바이트로 구성됩니다.  선행 바이트로 사용될 수 있는 바이트의 범위는 따로 지정되어 있습니다.  선행 바이트는 자신과 뒤에 오는 후행 바이트가 단일 2바이트 와이드 문자를 구성하도록 지정합니다.  사용자는 어떤 바이트가 선행 바이트인지 추적해야 합니다.  특정 멀티바이트 문자 집합에서 선행 바이트는 후행 바이트와 마찬가지로 일정한 범위 안에 포함됩니다.  이러한 범위가 겹치는 경우에는 특정 바이트가 선행 바이트인지 후행 바이트인지를 상황에 따라 판단해야 합니다.  
  
-   국제 시장을 대상으로 작성된 응용 프로그램의 MBCS 프로그래밍을 단순화하는 도구 지원  
  
     통합 소스 코드 편집기, 디버거, 명령줄 도구가 포함된 Visual C\+\+ 개발 시스템은 MBCS를 사용할 수 있는 Windows 운영 체제에서 실행될 경우 MBCS를 완벽하게 지원합니다.  자세한 내용은 [Visual C\+\+에서 MBCS 지원](../text/mbcs-support-in-visual-cpp.md)을 참조하십시오.  
  
> [!NOTE]
>  이 설명서에서는 멀티바이트 문자에 대한 모든 비 유니코드 지원을 설명하는 데 MBCS를 사용합니다.  Visual C\+\+에서 MBCS는 항상 DBCS를 의미합니다.  2바이트보다 큰 문자 집합은 지원되지 않습니다.  
  
 ASCII 문자 집합은 모든 멀티바이트 문자 집합의 부분 집합으로 정의됩니다.  많은 멀티바이트 문자 집합에서 0x00 – 0x7F 범위에 있는 각 문자는 ASCII 문자 집합에서 동일한 값을 갖는 문자와 같습니다.  예를 들어, ASCII와 MBCS 문자열에서 1바이트 **NULL** 문자\('\\0'\)는 값이 0x00이며 종료 Null 문자를 나타냅니다.  
  
## 참고 항목  
 [텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)   
 [국가별 사용](../text/international-enabling.md)