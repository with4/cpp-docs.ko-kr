---
title: "Accessing Version Information from Within Your Program | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerQueryValue"
  - "version information, accessing from within programs"
  - "GetFileVersionInfo"
  - "version information"
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Accessing Version Information from Within Your Program
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 프로그램 내에서 버전 정보에 액세스하려면  
  
1.  프로그램 내에서 버전 정보에 액세스하려는 경우 [GetFileVersionInfo](http://msdn.microsoft.com/library/windows/desktop/ms647003.aspx) 함수 및 [VerQueryValue](http://msdn.microsoft.com/library/windows/desktop/ms647464.aspx) 함수를 사용합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [버전 정보\(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)