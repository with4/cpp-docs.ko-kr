---
title: "&lt;see&gt;(Visual C++) | Microsoft Docs"
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
  - "<see>"
  - "see"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<see> C++ XML 태그"
  - "see C++ XML 태그"
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;see&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<see\> 태그를 사용하면 텍스트 내부에서 링크를 지정할 수 있습니다.  사용  [\<seealso\>](../ide/seealso-visual-cpp.md) 참고 항목 부분에 나타나는 텍스트를 나타냅니다.  
  
## 구문  
  
```  
<see cref="member"/>  
```  
  
#### 매개 변수  
 `member`  
 현재 컴파일 환경에서 호출될 수 있는 멤버 또는 필드에 대한 참조입니다.  이름을 단일 또는 이중 따옴표로 묶어야 합니다.  
  
 컴파일러는 지정 된 코드 요소가 존재 하 고 해결 확인 `member` 를 출력 XML의에서 요소 이름입니다.  검색 되지 않는 경우에 컴파일러에서 경고가 발생 `member`.  
  
## 설명  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
 볼  [\<summary\>](../ide/summary-visual-cpp.md) \<see\>를 사용 하는 예제입니다.  
  
 Visual C\+\+ 컴파일러에서 문서 주석을 통해 한번에 대 한 cref 참조를 해결 하려고 시도 합니다.  따라서 c \+ \+ 조회 규칙을 사용 하는 경우 기호 참조로 표시 하는 컴파일러에서 찾지는 확인 되지 않은.  자세한 내용은 [\<seealso\>](../ide/seealso-visual-cpp.md)를 참조하십시오.  
  
## 예제  
 컴파일러에 대 한 참조를 해결할 수 있도록 다음 샘플에서는 제네릭 형식에 대 한 cref 참조를 만들 수 있습니다 방법을 보여 줍니다.  
  
```  
// xml_see_cref_example.cpp  
// compile with: /LD /clr /doc  
// the following cref shows how to specify the reference, such that,  
// the compiler will resolve the reference  
/// <see cref="C{T}">  
/// </see>  
ref class A {};  
  
// the following cref shows another way to specify the reference,   
// such that, the compiler will resolve the reference  
/// <see cref="C < T >"/>  
  
// the following cref shows how to hard-code the reference  
/// <see cref="T:C`1">  
/// </see>  
ref class B {};  
  
/// <see cref="A">  
/// </see>  
/// <typeparam name="T"></typeparam>  
generic<class T>  
ref class C {};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)