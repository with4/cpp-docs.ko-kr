---
title: "&lt;param&gt;(Visual C++) | Microsoft Docs"
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
  - "param"
  - "<param>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<param> C++ XML 태그"
  - "param C++ XML 태그"
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;param&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메서드의 매개 변수 중 하나를 설명하려면 메서드 선언의 주석에서 \<param\> 태그를 사용해야 합니다.  
  
## 구문  
  
```  
<param name='name'>description</param>  
```  
  
#### 매개 변수  
 `name`  
 메서드 매개 변수의 이름입니다.  이름을 단일 또는 이중 따옴표로 묶어야 합니다.  검색 되지 않는 경우에 컴파일러에서 경고가 발생 `name`.  
  
 `description`  
 매개 변수에 대한 설명입니다.  
  
## 설명  
 \<param\>에 대 한 텍스트 IntelliSense에 표시 될 태그는  [개체 브라우저](http://msdn.microsoft.com/ko-kr/f89acfc5-1152-413d-9f56-3dc16e3f0470), 코드 주석 웹 보고서에.  
  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
  
```  
// xml_param_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_param_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <param name="Int1">Used to indicate status.</param>  
   void MyMethod(int Int1) {  
   }  
};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)