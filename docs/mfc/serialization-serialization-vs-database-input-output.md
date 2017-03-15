---
title: "Serialization: Serialization과 데이터베이스 입출력 비교 | Microsoft Docs"
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
  - "데이터베이스 응용 프로그램[C++], 파일 I/O와 serialization 비교"
  - "데이터베이스[C++], 입력/출력 처리"
  - "I/O[C++], serialization과 비교"
  - "serialization[C++], 데이터베이스 I/O와 비교"
ms.assetid: f1d23d77-4761-4a52-a7ea-54fc92d347ea
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Serialization: Serialization과 데이터베이스 입출력 비교
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains when to use document objects and serialization for file\-based input\/output \(I\/O\) and when other I\/O techniques are appropriate — because the application reads and writes data on a per\-transaction basis, as in database applications.  If you don't use serialization, you also won't need the File Open, Save, and Save As commands.  다음 내용에 대해 다룹니다.  
  
-   [Recommendations for handling input\/output](../mfc/recommendations-for-handling-input-output.md)  
  
-   [Handling the File menu in database applications](../mfc/file-menu-in-an-mfc-database-application.md)  
  
## 참고 항목  
 [Serialization](../mfc/serialization-in-mfc.md)