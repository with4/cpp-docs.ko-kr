---
title: "&lt;exception&gt;(Visual C++) | Microsoft Docs"
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
  - "exception"
  - "<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<exception> C++ XML 태그"
  - "exception C++ XML 태그"
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;exception&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

throw할 수 있는 예외를 \<exception\> 태그에 지정합니다.  이 태그는 메서드 정의에 적용됩니다.  
  
## 구문  
  
```  
<exception cref="member">description</exception>  
```  
  
#### 매개 변수  
 `member`  
 현재 컴파일 환경에 있는 예외에 대한 참조.  지정 된 예외가 존재 하 고 변환 컴파일러 이름 조회 규칙을 사용 하 여 확인 `member` 를 출력 XML의에서 정식 요소 이름입니다.  검색 되지 않는 경우에 컴파일러에서 경고가 발생 `member`.  
  
 이름을 단일 또는 이중 따옴표로 묶어야 합니다.  
  
 제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see\>](../ide/see-visual-cpp.md)를 참조하십시오.  
  
 `description`  
 설명.  
  
## 설명  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
 Visual C\+\+ 컴파일러에서 문서 주석을 통해 한번에 대 한 cref 참조를 해결 하려고 시도 합니다.  따라서 c \+ \+ 조회 규칙을 사용 하는 경우 기호 참조로 표시 하는 컴파일러에서 찾지는 확인 되지 않은.  자세한 내용은 [\<seealso\>](../ide/seealso-visual-cpp.md)를 참조하십시오.  
  
## 예제  
  
```  
// xml_exception_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_exception_tag.dll  
using namespace System;  
  
/// Text for class EClass.  
public ref class EClass : public Exception {  
   // class definition ...  
};  
  
/// <exception cref="System.Exception">Thrown when... .</exception>  
public ref class TestClass {  
   void Test() {  
      try {  
      }  
      catch(EClass^) {  
      }  
   }  
};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)