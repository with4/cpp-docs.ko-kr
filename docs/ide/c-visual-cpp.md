---
title: "&lt;c&gt;(Visual C++) | Microsoft Docs"
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
  - "<c>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<c> C++ XML 태그"
  - "c C++ XML 태그"
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;c&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<c\> 설명 안의 텍스트가 코드 표시 되도록 태그를 나타냅니다.  여러 줄을 코드로 표시하려면 [\<code\>](../ide/code-visual-cpp.md)를 사용합니다.  
  
## 구문  
  
```  
<c>text</c>  
```  
  
#### 매개 변수  
 `text`  
 코드로 나타낼 텍스트입니다.  
  
## 설명  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
  
```  
// xml_c_tag.cpp  
// compile with: /doc /LD  
// post-build command: xdcmake xml_c_tag.xdc  
  
/// Text for class MyClass.  
class MyClass {  
public:  
   int m_i;  
   MyClass() : m_i(0) {}  
  
   /// <summary><c>MyMethod</c> is a method in the <c>MyClass</c> class.  
   /// </summary>  
   int MyMethod(MyClass * a) {  
      return a -> m_i;  
   }  
};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)