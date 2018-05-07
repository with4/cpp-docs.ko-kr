---
title: '&lt;참조&gt; (Visual c + +) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <see>
- see
dev_langs:
- C++
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a03dd56320b948d47c765f253bf3e6b706ed2b56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltseegt-visual-c"></a>&lt;참조&gt; (Visual c + +)
\<see> 태그를 사용하면 텍스트 내부에서 링크를 지정할 수 있습니다. 사용 하 여 [ \<seealso >](../ide/seealso-visual-cpp.md) 참고 항목 섹션에 나타낼 수 있는 텍스트를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `member`  
 현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.  이름을 단일 또는 이중 따옴표로 묶습니다.  
  
 지정 된 코드 요소가 있으며 해결 컴파일러 확인 `member` 출력 XML에에서 요소 이름입니다.  `member`가 검색되지 않는 경우 컴파일러에서 경고가 발생합니다.  
  
## <a name="remarks"></a>설명  
 [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
 참조 [ \<요약 >](../ide/summary-visual-cpp.md) 사용 하는 예제에 대 한 \<참조 > 합니다.  
  
 Visual C++ 컴파일러에서는 문서 주석을 통해 단일 패스로 cref 참조를 확인하려고 합니다.  따라서 C++ 조회 규칙을 사용하는 경우 컴파일러에서 기호를 찾을 수 없으며 참조는 확인되지 않음으로 표시됩니다. 참조 [ \<seealso >](../ide/seealso-visual-cpp.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플은 제네릭 형식에 대 한 cref 참조를 확인할 수 있는 방법은 되도록, 컴파일러 참조를 확인 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)