---
title: '&lt;paramref&gt; (Visual c + +) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- paramref
- <paramref>
dev_langs:
- C++
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe6bb2d14b79e8080815967f3a666808f2b6efcc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltparamrefgt-visual-c"></a>&lt;paramref&gt; (Visual c + +)
\<paramref > 태그는 단어는 매개 변수를 표시 하는 방식이 제공 합니다. 다른 방식으로이 매개 변수 형식을 지정 하는.xml 파일을 처리할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `name`  
 참조할 매개 변수의 이름입니다.  이름을 단일 또는 이중 따옴표로 묶습니다.  `name`가 검색되지 않는 경우 컴파일러에서 경고가 발생합니다.  
  
## <a name="remarks"></a>설명  
 [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
  
```  
// xml_paramref_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_paramref_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <summary>MyMethod is a method in the MyClass class.  
   /// The <paramref name="Int1"/> parameter takes a number.  
   /// </summary>  
   void MyMethod(int Int1) {}  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)