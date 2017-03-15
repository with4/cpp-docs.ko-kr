---
title: "&lt;remarks&gt;(Visual C++) | Microsoft Docs"
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
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<remarks> C++ XML 태그"
  - "remarks C++ XML 태그"
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;remarks&gt;(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<remarks\> 태그는 형식에 대한 정보를 추가하여 [\<summary\>](../ide/summary-visual-cpp.md)에 지정한 정보를 보충하는 데 사용합니다.  이 정보가 표시 되는  [개체 브라우저](http://msdn.microsoft.com/ko-kr/f89acfc5-1152-413d-9f56-3dc16e3f0470) 및 코드 주석 웹 보고서에.  
  
## 구문  
  
```  
<remarks>description</remarks>  
```  
  
#### 매개 변수  
 `description`  
 멤버에 대한 설명입니다.  
  
## 설명  
 [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
  
```  
// xml_remarks_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_remarks_tag.dll  
  
using namespace System;  
  
/// <summary>  
/// You may have some primary information about this class.  
/// </summary>  
/// <remarks>  
/// You may have some additional information about this class.  
/// </remarks>  
public ref class MyClass {};  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)