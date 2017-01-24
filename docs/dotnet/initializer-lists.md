---
title: "이니셜라이저 목록 | Microsoft Docs"
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
  - "이니셜라이저 목록"
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이니셜라이저 목록
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이제 생성자의 이니셜라이저 목록이 기본 클래스 생성자보다 먼저 호출됩니다.  
  
## 설명  
 Visual C\+\+ 2005 이전에는 Managed Extensions for C\+\+를 사용하여 컴파일할 때 기본 클래스 생성자가 이니셜라이저 목록보다 먼저 호출되었습니다.  이제는 **\/clr**로 컴파일할 때 이니셜라이저 목록이 먼저 호출됩니다.  
  
## 참고 항목  
 [일반적인 언어 변경 사항](../dotnet/general-language-changes-cpp-cli.md)