---
title: "CObject 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject 클래스"
  - "파생 클래스, CObject에서"
  - "예제[MFC], CObject"
  - "MFC, 기본 클래스"
  - "MFC에 대한 루트 기본 클래스"
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObject 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CObject](../mfc/reference/cobject-class.md) is the root base class for most of the Microsoft Foundation Class Library \(MFC\).  The `CObject` class contains many useful features that you may want to incorporate into your own program objects, including serialization support, run\-time class information, and object diagnostic output.  If you derive your class from `CObject`, your class can exploit these `CObject` features.  
  
## 수행할 작업  
  
-   [Derive a class from CObject](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Add support for run\-time class information, dynamic creation, and serialization to my derived class](../mfc/specifying-levels-of-functionality.md)  
  
-   [Access run\-time class information](../mfc/accessing-run-time-class-information.md)  
  
-   [Create objects dynamically](../mfc/dynamic-object-creation.md)  
  
-   [Dump the object's data for diagnostic purposes](http://msdn.microsoft.com/ko-kr/727855b1-5a83-44bd-9fe3-f1d535584b59)  
  
-   Validate the object's internal state \(see [MFC ASSERT\_VALID and CObject::AssertValid](http://msdn.microsoft.com/ko-kr/7654fb75-9e9a-499a-8165-0a96faf2d5e6)\)  
  
-   [Have the class serialize itself to persistent storage](../mfc/serialization-in-mfc.md)  
  
-   See a list of [CObject Frequently Asked Questions](../mfc/cobject-class-frequently-asked-questions.md)  
  
## 참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)   
 [CRuntimeClass Structure](../mfc/reference/cruntimeclass-structure.md)   
 [파일](../mfc/files-in-mfc.md)   
 [Serialization](../mfc/serialization-in-mfc.md)