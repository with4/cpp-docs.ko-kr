---
title: "&lt;permission&gt;(Visual C++) | Microsoft Docs"
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
  - "permission"
  - "<permission>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<permission> C++ XML 태그"
  - "permission C++ XML 태그"
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;permission&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<permission\> 태그를 사용하면 멤버 액세스를 문서화할 수 있습니다.  <xref:System.Security.PermissionSet>멤버에 액세스를 지정할 수 있습니다.  
  
## 구문  
  
```  
<permission cref="member">description</permission>  
```  
  
#### 매개 변수  
 `member`  
 현재 컴파일 환경에서 호출될 수 있는 멤버 또는 필드에 대한 참조입니다.  컴파일러는 지정된 코드 요소가 있는지 확인한 다음 `member`를 출력 XML의 정식 요소 이름으로 변환합니다.  이름을 단일 또는 이중 따옴표로 묶어야 합니다.  
  
 검색 되지 않는 경우에 컴파일러에서 경고가 발생 `member`.  
  
 제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see\>](../ide/see-visual-cpp.md)를 참조하십시오.  
  
 `description`  
 멤버 액세스에 대한 설명입니다.  
  
## 설명  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
 Visual C\+\+ 컴파일러에서 문서 주석을 통해 한번에 대 한 cref 참조를 해결 하려고 시도 합니다.  따라서 c \+ \+ 조회 규칙을 사용 하는 경우 기호 참조로 표시 하는 컴파일러에서 찾지는 확인 되지 않은.  자세한 내용은 [\<seealso\>](../ide/seealso-visual-cpp.md)를 참조하십시오.  
  
## 예제  
  
```  
// xml_permission_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_permission_tag.dll  
using namespace System;  
/// Text for class TestClass.  
public ref class TestClass {  
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>  
   void Test() {}  
};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)