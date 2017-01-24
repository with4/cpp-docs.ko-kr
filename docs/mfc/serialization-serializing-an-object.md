---
title: "Serialization: 개체 Serialize | Microsoft Docs"
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
  - "개체[C++], serialize"
  - "serialization[C++], 개체"
  - "개체 serialize[C++]"
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Serialization: 개체 Serialize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 [직렬화: 직렬화 클래스 만들기](../mfc/serialization-making-a-serializable-class.md) 문서는 직렬화가능한 클래스를 만드는 방법을 보여줍니다.  먼저 직렬화가능한 클래스를 만들고, [CArchive](../mfc/reference/carchive-class.md) 개체에 대한 파일로부터, 클래스의 개체들을 직렬화할 수 있습니다.  이 문서는 다음을 설명합니다:  
  
-   [CArchive 개체가 무엇인지](../mfc/what-is-a-carchive-object.md)  
  
-   [CArchive를 만드는 두가지 방법](../mfc/two-ways-to-create-a-carchive-object.md).  
  
-   [CArchive를 사용 하는 방법 \<\< 과 \>\>연산자들](../mfc/using-the-carchive-output-and-input-operators.md).  
  
-   [archive를 통한 CObjects의 저장과 로드](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 프레임워크가 직렬화할수 있는 문서들의 보관소를 만들거나 명시적으로 `CArchive` 개체를 만들 수 있습니다.  `CArchive` 에 대한 \>\> 연산자들과 \<\< 를 사용하거나, 때로는 `CObject` 로 파생된 클래스의 `Serialize` 함수를 호출함으로써 직렬화가능한 개체와 파일 사이에 데이터를 전송할 수 있습니다.  
  
## 참고 항목  
 [Serialization](../mfc/serialization-in-mfc.md)