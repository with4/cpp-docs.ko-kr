---
title: '&lt;include&gt;(Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- include
- <include>
dev_langs:
- C++
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4c1a75acb89d9510dd7f489e5d0d582611da8de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330429"
---
# <a name="ltincludegt-visual-c"></a>&lt;include&gt;(Visual C++)
\<include> 태그를 사용하면 소스 코드의 형식과 멤버를 설명하는 다른 파일의 주석을 참조할 수 있습니다. 소스 코드 파일에 직접 문서 주석을 포함하는 대신 사용되는 대안입니다.  예를 들어 \<include>를 사용하여 팀이나 회사 전체에서 사용되는 표준 "상용구" 주석을 삽입할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### <a name="parameters"></a>매개 변수  
 `filename`  
 문서가 포함된 파일의 이름입니다. 경로를 사용하여 파일 이름을 정규화할 수 있습니다.  이름을 단일 또는 이중 따옴표로 묶습니다.  `filename`가 검색되지 않는 경우 컴파일러에서 경고가 발생합니다.  
  
 `tagpath`  
 파일에 포함된 원하는 노드 집합을 선택하는 유효한 XPath 식입니다.  
  
 `name`  
 주석 앞에 오는 태그의 이름 지정자입니다. `name`에는 `id`가 있습니다.  
  
 `id`  
 주석 앞에 오는 태그의 ID입니다.  이름을 단일 또는 이중 따옴표로 묶습니다.  
  
## <a name="remarks"></a>설명  
 \<include> 태그는 XML XPath 구문을 사용합니다. \<include>를 사용하여 사용자 지정하는 방법은 XPath 설명서를 참조하세요.  
  
 [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예  
 다중 파일 예제입니다. \<include>를 사용하는 첫 번째 파일에는 다음과 같은 문서 주석이 포함되어 있습니다.  
  
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
  
 두 번째 파일인 xml_include_tag.doc에는 다음과 같은 문서 주석이 포함되어 있습니다.  
  
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
  
## <a name="program-output"></a>프로그램 출력  
  
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
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)