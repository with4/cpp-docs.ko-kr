---
title: "CString Semantics | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "대입문, assigning CString objects"
  - "CString objects, assignment semantics"
  - "semantics in Cstring"
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CString Semantics
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

경우에  [CString](../atl-mfc-shared/reference/cstringt-class.md) 개체는 확장할 수 있는 동적 개체, 이러한 기본 제공 기본 형식 및 간단한 클래스와 같은 역할을 합니다.  각 `CString` 개체는 고유 값을 나타냅니다.  `CString`개체의 실제 문자열 대신 문자열 포인터로 이용해 야 합니다.  
  
 지정할 수 있는  **CString**  다른 개체입니다.  그러나 수정 하면 두 가지 `CString` 개체를 다른 `CString` 개체는 수정 되지 다음 예제에서와 같이.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/CPP/cstring-semantics_1.cpp)]  
  
 참고가 예제에는 두 `CString` 개체 간주 "같음" 같은 문자열을 나타내므로.  `CString` 클래스는 같음 연산자를 오버 로드 \(`==`\) 2 비교할 `CString` 개체 id \(주소\) 대신 값 \(내용\)에 따라.  
  
## 참고 항목  
 [문자열](../atl-mfc-shared/strings-atl-mfc.md)