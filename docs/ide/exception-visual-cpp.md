---
title: "&lt;예외&gt; (Visual c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- exception
- <exception>
dev_langs: C++
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c07dde806938b38dd55a3258b3724b0937d5601d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ltexceptiongt-visual-c"></a>&lt;예외&gt; (Visual c + +)
\<exception> 태그를 사용하면 throw할 수 있는 예외를 지정할 수 있습니다. 이 태그 메서드 정의에 적용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `member`  
 현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조입니다. 이름 조회 규칙을 사용 하는 컴파일러 확인 주어진된 예외 존재 한 변환 `member` 출력 XML에에서 정식 요소 이름입니다.  `member`가 검색되지 않는 경우 컴파일러에서 경고가 발생합니다.  
  
 이름을 단일 또는 이중 따옴표로 묶습니다.  
  
 제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see>](../ide/see-visual-cpp.md)를 참조하세요.  
  
 `description`  
 설명입니다.  
  
## <a name="remarks"></a>설명  
 [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
 Visual C++ 컴파일러에서는 문서 주석을 통해 단일 패스로 cref 참조를 확인하려고 합니다.  따라서 C++ 조회 규칙을 사용하는 경우 컴파일러에서 기호를 찾을 수 없으며 참조는 확인되지 않음으로 표시됩니다. 참조 [ \<seealso >](../ide/seealso-visual-cpp.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
  
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
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)