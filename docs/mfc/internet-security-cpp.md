---
title: "인터넷 보안(C++) | Microsoft Docs"
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
  - "코드 액세스 보안[C++], 인터넷 보안 고려 사항"
  - "코드 서명[C++]"
  - "코드 서명[C++], 인터넷 보안"
  - "디지털 서명, 인터넷 보안"
  - "인터넷 응용 프로그램, 보안"
  - "샌드박싱"
  - "보안[MFC]"
  - "보안[MFC], 인터넷"
  - "웹 응용 프로그램 보안"
  - "웹 응용 프로그램 보안, 인터넷 보안 방법"
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 인터넷 보안(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Code safety is a major issue for developers and for users of Internet applications.  There are risks: malicious code, code that has been tampered with, and code from unknown sites or authors.  
  
 There are two basic approaches to security when developing for the Internet.  The first is called "sandboxing." In this approach, an application is restricted to a particular set of APIs, and excluded from potentially dangerous ones such as file I\/O where a program could destroy data on a user's computer.  The second is implemented using digital signatures.  This approach is referred to as "shrinkwrap" for the Internet.  Code is verified and signed using private key\/public key technology.  Before the code is run, its digital signature is verified to ensure that the code is from a known authenticated source, and that the code has not been altered since it has been signed.  
  
 In the first case, you trust that the application will not do any harm and you trust the origin of the application.  In the second, digital signatures are used to verify authenticity.  Digital signing is an industry standard used to identify and provide details about the publisher of the code.  Its technology is based on standards, including RSA and X.509.  Browsers typically allow users to choose if they want to download and run code of unknown origin.  
  
 Additional information about code signing and other security measures is available on the Web.  Information can be accessed through the MSDN Online Web Workshop site at [http:\/\/msdn.microsoft.com\/](http://msdn.microsoft.com/), or through the World Wide Web consortium at [http:\/\/www.w3.org\/](http://www.w3.org/).  
  
## 참고 항목  
 [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)   
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)