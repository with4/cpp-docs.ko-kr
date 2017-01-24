---
title: "1단계 및 2단계 개체 생성 | Microsoft Docs"
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
  - "개체 만들기, 그래픽 개체"
  - "개체[C++], 그래픽 개체 만들기"
  - "개체[C++], 그래픽 개체"
  - "1단계 및 2단계 개체 생성"
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1단계 및 2단계 개체 생성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You have a choice between two techniques for creating graphic objects, such as pens and brushes:  
  
-   *One\-stage construction*: Construct and initialize the object in one stage, all with the constructor.  
  
-   *Two\-stage construction*: Construct and initialize the object in two separate stages.  The constructor creates the object and an initialization function initializes it.  
  
 Two\-stage construction is always safer.  In one\-stage construction, the constructor could throw an exception if you provide incorrect arguments or memory allocation fails.  That problem is avoided by two\-stage construction, although you do have to check for failure.  In either case, destroying the object is the same process.  
  
> [!NOTE]
>  These techniques apply to creating any objects, not just graphic objects.  
  
## Example of Both Construction Techniques  
 The following brief example shows both methods of constructing a pen object:  
  
 [!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/CPP/one-stage-and-two-stage-construction-of-objects_1.cpp)]  
  
### 추가 정보  
  
-   [Graphic objects](../mfc/graphic-objects.md)  
  
-   [Selecting a graphic object into a device context](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Device contexts](../mfc/device-contexts.md)  
  
-   [Drawing in a View](../mfc/drawing-in-a-view.md)  
  
## 참고 항목  
 [그래픽 개체](../mfc/graphic-objects.md)