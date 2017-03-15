---
title: "&lt;example&gt;(Visual C++) | Microsoft Docs"
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
  - "<example>"
  - "example"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<example> C++ XML 태그"
  - "example C++ XML 태그"
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;example&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<example\> 태그를 사용하면 메서드나 기타 라이브러리 멤버의 사용 방법에 대한 예제를 지정할 수 있습니다.  일반적으로이 사용 하는 작업도 하는  [\<code\>](../ide/code-visual-cpp.md) 태그.  
  
## 구문  
  
```  
<example>description</example>  
```  
  
#### 매개 변수  
 `description`  
 코드 예제에 대한 설명입니다.  
  
## 설명  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
  
```  
// xml_example_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_example_tag.dll  
  
/// Text for class MyClass.  
public ref class MyClass {  
public:  
   /// <summary>  
   /// GetZero method  
   /// </summary>  
   /// <example> This sample shows how to call the GetZero method.  
   /// <code>  
   /// int main()   
   /// {  
   ///    return GetZero();  
   /// }  
   /// </code>  
   /// </example>  
   static int GetZero() {  
      return 0;  
   }  
};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)