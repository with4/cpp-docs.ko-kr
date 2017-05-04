---
title: "Exception::Message 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::Message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::Message 속성"
ms.assetid: ad1199cd-0889-4803-ad0d-a3a7b3c51891
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::Message 속성
오류를 설명하는 메시지입니다.  
  
## 구문  
  
```cpp  
public:property String^ Message;  
```  
  
## 속성 값  
 Windows 런타임에서 발생하는 예외의 경우, 이것은 오류에 대한 시스템 제공 설명입니다.  
  
## 설명  
 [!INCLUDE[win8](../cppcx/includes/win8-md.md)]에서는 해당 버전의 Windows 런타임이 HRESULTS로만 ABI 전체에 전송되므로 이 속성은 읽기 전용입니다.[!INCLUDE[win81](../cppcx/includes/win81-md.md)]에서는 보다 다양한 예외 정보가 ABI 전반에서 전송되며 다른 구성 요소에서 프로그래밍 방식으로 액세스할 수 있는 사용자 지정 메시지를 사용자가 제공할 수 있습니다. 자세한 내용은 [예외\(C\+\+\/CX\)](../cppcx/exceptions-c-cx.md)를 참조하세요.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::Exception 클래스](../cppcx/platform-exception-class.md)