---
title: 문서 주석에 대한 권장 태그(Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b25ad029a59c4b23bcab093b3742f16f7ca9175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328622"
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>문서 주석에 대한 권장 태그(Visual C++)
Visual C++ 컴파일러는 코드에서 문서 주석을 처리하고 각 컴파일 대상에 대해 .xdc 파일을 만들고, xdcmake.exe는 .xdc 파일을 xml 파일로 처리합니다. 문서를 만들기 위해 .xml 파일을 처리하는 것은 사이트에서 구현해야 하는 세부 사항입니다.  
  
 태그는 형식, 형식 멤버와 같은 구문에서 처리됩니다.  
  
 태그는 형식 또는 멤버 바로 앞에 와야 합니다.  
  
> [!NOTE]
>  문서 주석은 속성 및 이벤트에 대한 네임스페이스 또는 라인 외부 정의에 적용할 수 없습니다. 문서 주석은 클래스 내 선언에 있어야 합니다.  
  
 컴파일러는 유효한 XML인 태그를 모두 처리합니다. 다음 태그는 사용자 문서에서 일반적으로 사용되는 기능을 제공합니다.  
  
||||  
|-|-|-|  
|[\<c>](../ide/c-visual-cpp.md)|[\<code>](../ide/code-visual-cpp.md)|[\<example>](../ide/example-visual-cpp.md)|  
|[\<exception>](../ide/exception-visual-cpp.md)1|[\<include>](../ide/include-visual-cpp.md)1|[\<list>](../ide/list-visual-cpp.md)|  
|[\<para>](../ide/para-visual-cpp.md)|[\<param>](../ide/param-visual-cpp.md)1|[\<paramref>](../ide/paramref-visual-cpp.md)1|  
|[\<permission>](../ide/permission-visual-cpp.md)1|[\<remarks>](../ide/remarks-visual-cpp.md)|[\<returns>](../ide/returns-visual-cpp.md)|  
|[\<see>](../ide/see-visual-cpp.md)1|[\<seealso>](../ide/seealso-visual-cpp.md)1|[\<summary>](../ide/summary-visual-cpp.md)|  
|[\<value>](../ide/value-visual-cpp.md)|||  
  
 1. 컴파일러가 구문을 확인합니다.  
  
 현재 릴리스에서 Visual C++ 컴파일러는 다른 Visual Studio 컴파일러에서 지원하는 `<paramref>` 태그를 지원하지 않습니다. Visual C++는 이후 릴리스에서 `<paramref>`를 지원할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)