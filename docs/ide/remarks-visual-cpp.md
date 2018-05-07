---
title: '&lt;주의&gt; (Visual c + +) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- remarks
- <remarks>
dev_langs:
- C++
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 380a2c27a761154e59826259d3e1e682ae7fbd87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltremarksgt-visual-c"></a>&lt;주의&gt; (Visual c + +)
\<remarks> 태그는 형식에 대한 정보를 추가하여 [\<summary>](../ide/summary-visual-cpp.md)로 지정된 정보를 보완하기 위해 사용됩니다. 이 정보에 표시 되는 [개체 브라우저](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470) 및 코드 주석 웹 보고서입니다.  
  
## <a name="syntax"></a>구문  
  
```  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `description`  
 멤버에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  
 [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)