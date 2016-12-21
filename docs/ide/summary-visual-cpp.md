---
title: "&lt;summary&gt;(Visual C++) | Microsoft Docs"
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
  - "<summary>"
  - "summary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<summary> C++ XML 태그"
  - "summary C++ XML 태그"
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;summary&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 또는 형식 멤버를 설명하려면 \<summary\> 태그를 사용해야 합니다.  형식에 대한 설명을 보충하는 정보를 추가하려면 [\<remarks\>](../ide/remarks-visual-cpp.md)를 사용합니다.  
  
## 구문  
  
```  
<summary>description</summary>  
```  
  
#### 매개 변수  
 `description`  
 개체에 대한 요약입니다.  
  
## 설명  
 \<summary\>에 대 한 텍스트 태그, IntelliSense에서 형식에 대 한 정보의 유일한 소스가 고도 표시 됩니다의  [개체 브라우저](http://msdn.microsoft.com/ko-kr/f89acfc5-1152-413d-9f56-3dc16e3f0470) 및 코드 주석 웹 보고서에.  
  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
  
```  
// xml_summary_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_summary_tag.dll  
  
/// Text for class MyClass.  
public ref class MyClass {  
public:  
   /// <summary>MyMethod is a method in the MyClass class.  
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>  
   /// <seealso cref="MyClass::MyMethod2"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void MyMethod2() {}  
};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)