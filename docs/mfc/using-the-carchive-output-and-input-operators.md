---
title: "CArchive &lt;&lt; 및 &gt;&gt; 연산자 사용 | Microsoft Docs"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive 클래스, 연산자"
  - "CArchive 클래스, 개체 저장 및 로드"
  - "개체[C++], 이전에 저장한 값에서 로드"
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArchive &lt;&lt; 및 &gt;&gt; 연산자 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CArchive` provides \<\< and \>\> operators for writing and reading simple data types as well as `CObject`s to and from a file.  
  
#### To store an object in a file via an archive  
  
1.  The following example shows how to store an object in a file via an archive:  
  
     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_1.cpp)]  
  
#### To load an object from a value previously stored in a file  
  
1.  The following example shows how to load an object from a value previously stored in a file:  
  
     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_2.cpp)]  
  
 Usually, you store and load data to and from a file via an archive in the `Serialize` functions of `CObject`\-derived classes, which you must have declared with the **DECLARE\_SERIALIZE** macro.  A reference to a `CArchive` object is passed to your `Serialize` function.  You call the `IsLoading` function of the `CArchive` object to determine whether the `Serialize` function has been called to load data from the file or store data to the file.  
  
 The `Serialize` function of a serializable `CObject`\-derived class typically has the following form:  
  
 [!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_3.cpp)]  
  
 The above code template is exactly the same as the one AppWizard creates for the `Serialize` function of the document \(a class derived from **CDocument\)**.  This code template helps you write code that is easier to review, because the storing code and the loading code should always be parallel, as in the following example:  
  
 [!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_4.cpp)]  
  
 The library defines **\<\<** and **\>\>** operators for `CArchive` as the first operand and the following data types and class types as the second operand:  
  
||||  
|-|-|-|  
|`CObject*`|**SIZE and CSize**|**float**|  
|**WORD**|`CString`|**POINT** and `CPoint`|  
|`DWORD`|**BYTE**|`RECT` 및 `CRect`|  
|**Double**|**LONG**|`CTime` 및 `CTimeSpan`|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  Storing and loading `CObject`s via an archive requires extra consideration.  For more information, see [Storing and Loading CObjects via an Archive](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 The **CArchive \<\<** and **\>\>** operators always return a reference to the `CArchive` object, which is the first operand.  This enables you to chain the operators, as illustrated below:  
  
 [!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_5.cpp)]  
  
## 참고 항목  
 [Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)