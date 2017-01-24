---
title: "&lt;include&gt;(Visual C++) | Microsoft Docs"
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
  - "include"
  - "<include>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<include> C++ XML 태그"
  - "include C++ XML 태그"
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;include&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<include\> 태그를 사용하면 소스 코드의 형식과 멤버를 설명하는 다른 파일의 주석을 참조할 수 있습니다.  이렇게 하면 소스 코드 파일에 직접 문서 주석을 배치하지 않아도 됩니다.  예를 들어, 사용할 수 있습니다 \<include\> 팀 또는 회사 전체에서 사용 되는 표준 "상용구" 주석을 삽입.  
  
## 구문  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### 매개 변수  
 `filename`  
 문서를 포함할 파일 이름입니다.  파일 이름은 path로 한정될 수 있습니다.  이름을 단일 또는 이중 따옴표로 묶어야 합니다.  검색 되지 않는 경우에 컴파일러에서 경고가 발생 `filename`.  
  
 `tagpath`  
 원하는 노드는 파일에 포함 된 집합을 선택 하는 유효한 XPath 식입니다.  
  
 `name`  
 주석 앞에 오는 태그의 이름 지정자입니다. `name`에는 `id`가 있어야 합니다.  
  
 `id`  
 주석 앞에 오는 태그의 ID입니다.  이름을 단일 또는 이중 따옴표로 묶어야 합니다.  
  
## 설명  
 \<include\> 태그는 XML XPath 구문을 사용합니다.  사용 하 여 사용자 지정 하는 방법에 대 한 XPath 문서를 참조 하십시오 \<include\>.  
  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 아래 예제는 여러 개의 파일로 구성됩니다.  사용 하 여 첫 번째 파일 \<include\> 다음 문서 주석이 포함 되어 있습니다.  
  
```  
// xml_include_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_include_tag.dll  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />  
public ref class Test {  
   void TestMethod() {  
   }  
};  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />  
public ref class Test2 {  
   void Test() {  
   }  
};  
```  
  
 두 번째 파일 xml\_include\_tag.doc에는 다음 문서 주석이 있습니다.  
  
```  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## 프로그램 출력  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>t2</name>  
    </assembly>  
    <members>  
        <member name="T:Test">  
            <summary>  
The summary for this type.  
</summary>  
        </member>  
        <member name="T:Test2">  
            <summary>  
The summary for this other type.  
</summary>  
        </member>  
    </members>  
</doc>  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)