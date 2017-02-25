---
title: "문자 집합 이식성의 이점 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "문자 집합[C++], 장점"
  - "이식성[C++], 문자 집합"
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# 문자 집합 이식성의 이점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 응용 프로그램을 국제화하지 않더라도 MFC와 C 런타임 이식성 기능을 활용할 수 있습니다.  
  
-   이식 가능한 코딩은 기본 코드에 유연성을 제공하므로  나중에 코드를 유니코드나 MBCS로 쉽게 이동할 수 있습니다.  
  
-   유니코드를 사용하면 보다 효율적인 Windows 2000용 응용 프로그램이 됩니다.  Windows 2000은 유니코드를 사용하기 때문에 운영 체제에서 비 유니코드 문자열을 주고 받을 때에는 오버 헤드를 발생시키는 변환 과정을 거쳐야 합니다.  
  
-   MBCS를 사용하면 Windows 2000 이외의 Win32 플랫폼\(예: Windows 95 또는 Windows 98\) 국제 시장을 지원할 수 있습니다.  
  
## 참고 항목  
 [유니코드 및 MBCS](../text/unicode-and-mbcs.md)   
 [유니코드 지원](../text/support-for-unicode.md)