---
title: "인터넷의 비동기 모니커 | Microsoft Docs"
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
  - "ActiveX 컨트롤[C++], 비동기"
  - "비동기 모니커[C++]"
  - "인터넷 리소스 및 비동기 모니커 다운로드"
  - "인터넷[C++], 비동기 다운로드"
  - "MFC[C++], 비동기 모니커"
  - "최적화[C++], 인터넷에서 비동기 다운로드"
  - "웹 응용 프로그램[C++], 비동기"
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 인터넷의 비동기 모니커
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The Internet requires new approaches to application design because of its slow network access.  Applications should perform network access asynchronously to avoid stalling the user interface.  The MFC class [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) provides asynchronous support for downloading files.  
  
 With asynchronous monikers, you can extend your COM application to download asynchronously across the Internet and to provide progressive rendering of large objects such as bitmaps and VRML objects.  Asynchronous monikers enable an ActiveX control property or a file on the Internet to be downloaded without blocking the response of the user interface.  
  
## Advantages of Asynchronous Monikers  
 You can use asynchronous monikers to:  
  
-   Download code and files without blocking.  
  
-   Download properties in ActiveX controls without blocking.  
  
-   Receive notifications of downloading progress.  
  
-   Track progress and ready state information.  
  
-   Provide status information to the user about progress.  
  
-   Allow the user to cancel a download at any time.  
  
## MFC Classes for Asynchronous Monikers  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) is derived from [CMonikerFile](../mfc/reference/cmonikerfile-class.md), which in turn is derived from [COleStreamFile](../mfc/reference/colestreamfile-class.md).  A `COleStreamFile` object represents a stream of data; a `CMonikerFile` object uses an `IMoniker` to obtain the data, and a `CAsyncMonikerFile` object does so asynchronously.  
  
 Asynchronous monikers are used primarily in Internet\-enabled applications and ActiveX controls to provide a responsive user interface during file transfers.  A prime example of this is the use of [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) to provide asynchronous properties for ActiveX controls.  
  
## MFC Classes for Data Paths in ActiveX Controls  
 The MFC classes `CDataPathProperty` and [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) implement ActiveX control properties that can be loaded asynchronously.  Asynchronous properties are loaded after synchronous initiation.  Asynchronous ActiveX controls repeatedly invoke a callback to indicate availability of new data during a lengthy property exchange process.  
  
 `CDataPathProperty`는 `CAsyncMonikerFile`에서 파생됩니다.  `CCachedDataPathProperty`는 `CDataPathProperty`에서 파생됩니다.  To implement asynchronous properties in your ActiveX controls, derive a class from `CDataPathProperty` or `CCachedDataPathProperty`, and override [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) and other notifications you wish to receive.  
  
#### To download a file using asynchronous monikers  
  
1.  Declare a class derived from [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
2.  Override [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) to display the data.  
  
3.  Override other member functions, including [OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md), [OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md), and [OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md).  
  
4.  Declare an instance of this class and use it to open URLs.  
  
 For information about downloading asynchronously in an ActiveX control, see [ActiveX Controls on the Internet](../mfc/activex-controls-on-the-internet.md).  
  
## 참고 항목  
 [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)   
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)