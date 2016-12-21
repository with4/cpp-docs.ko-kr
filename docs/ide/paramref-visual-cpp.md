---
title: "&lt;paramref&gt;(Visual C++) | Microsoft Docs"
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
  - "paramref"
  - "<paramref>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<paramref> C++ XML 태그"
  - "paramref C++ XML 태그"
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;paramref&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<paramref\> 태그를 사용 하면 특정 단어가 매개 변수임을 나타낼 수 있습니다.  이 매개 변수를 다른 방식으로 서식화 서식을 지정 하는.xml 파일을 처리할 수 있습니다.  
  
## 구문  
  
```  
<paramref name="name"/>  
```  
  
#### 매개 변수  
 `name`  
 참조할 매개 변수의 이름입니다.  이름을 단일 또는 이중 따옴표로 묶어야 합니다.  검색 되지 않는 경우에 컴파일러에서 경고가 발생 `name`.  
  
## 설명  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
  
```  
// xml_paramref_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_paramref_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <summary>MyMethod is a method in the MyClass class.  
   /// The <paramref name="Int1"/> parameter takes a number.  
   /// </summary>  
   void MyMethod(int Int1) {}  
};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)