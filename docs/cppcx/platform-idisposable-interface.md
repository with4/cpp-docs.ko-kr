---
title: "Platform::IDisposable 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IDisposable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IDisposable 인터페이스"
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 2
---
# Platform::IDisposable 인터페이스
관리되지 않는 리소스를 해제하는 데 사용됩니다.  
  
## 구문  
  
```cpp  
public interface class IDisposable  
```  
  
## 특성  
 **GuidAttribute**\("de0cbaea\-8065\-4a45\-b196\-c9d443f9bab3"\)  
  
 **VersionAttribute**\(NTDDI\_WIN8\)  
  
## 멤버  
 IDisposable 인터페이스는 IUnknown 인터페이스에서 상속됩니다. IDisposable에는 다음 형식의 멤버도 있습니다.  
  
 **메서드**  
  
 IDisposable 인터페이스에는 다음 메서드가 있습니다.  
  
|메서드|설명|  
|---------|--------|  
|HYPERLINK "http:\/\/msdnpreview.redmond.corp.microsoft.com\/en\-us\/library\/windows\/apps\/platform.idisposable.dispose.aspx" Dispose|관리되지 않는 리소스를 해제하는 데 사용됩니다.|  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform