---
title: "&lt;seealso&gt;(Visual C++) | Microsoft Docs"
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
  - "<seealso>"
  - "seealso"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<seealso> C++ XML 태그"
  - "seealso C++ XML 태그"
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;seealso&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<seealso\> 태그를 사용하면 참고 항목 부분에 나타나는 텍스트를 지정할 수 있습니다.  텍스트 내부에서 링크를 지정하려면 [\<see\>](../ide/see-visual-cpp.md)를 사용합니다.  
  
## 구문  
  
```  
<seealso cref="member"/>  
```  
  
#### 매개 변수  
 `member`  
 현재 컴파일 환경에서 호출될 수 있는 멤버 또는 필드에 대한 참조입니다.  이름을 단일 또는 이중 따옴표로 묶어야 합니다.  
  
 컴파일러는 지정 된 코드 요소가 존재 하 고 해결 확인 `member` 를 출력 XML의에서 요소 이름입니다.  검색 되지 않는 경우에 컴파일러에서 경고가 발생 `member`.  
  
 제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see\>](../ide/see-visual-cpp.md)를 참조하십시오.  
  
## 설명  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
 볼 [\<summary\>](../ide/summary-visual-cpp.md) \<seealso\>를 사용 하는 예제입니다.  
  
 Visual C\+\+ 컴파일러에서 문서 주석을 통해 한번에 대 한 cref 참조를 해결 하려고 시도 합니다.  따라서 c \+ \+ 조회 규칙을 사용 하는 경우 기호 참조로 표시 하는 컴파일러에서 찾지는 확인 되지 않은.  
  
## 예제  
 다음 예제는 확인할 수 없는 기호에서 cref 참조 됩니다.  XML 주석 cref B::Test 하 수 `<seealso cref="!:B::Test" />`, a::test에 대 한 참조가 제대로 구성 되어 있지만 `<seealso cref="M:A.Test" />`.  
  
```  
// xml_seealso_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_seealso_tag.dll  
  
/// Text for class A.  
public ref struct A {  
   /// <summary><seealso cref="A::Test"/>  
   /// <seealso cref="B::Test"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void Test() {}  
};  
  
/// Text for class B.  
public ref struct B {  
   void Test() {}  
};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)