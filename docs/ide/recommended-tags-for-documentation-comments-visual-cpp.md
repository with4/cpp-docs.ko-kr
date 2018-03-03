---
title: "문서 주석 (Visual c + +)에 대 한 권장 태그 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c1b0e762ec2167a988e8e18f3dce932214716c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>문서 주석에 대한 권장 태그(Visual C++)
Visual c + + 컴파일러 코드에서 문서 주석을 처리 하 고 각 컴파일 대상에 대 한.xdc 파일을 만듭니다. 및 xdcmake.exe.xdc 파일.xml 파일을 처리 합니다. 사이트에서 구현 해야 하는 세부는 문서를 만들.xml 파일을 처리 합니다.  
  
 태그에는 형식 멤버 및 형식 등과 같은 구문에서 처리 됩니다.  
  
 태그는 형식 또는 멤버 바로 앞에 야 합니다.  
  
> [!NOTE]
>  문서 주석은 적용할 수 없습니다 또는 네임 스페이스에 속성 및 이벤트에 대 한 라인 정의에서 문서 주석 클래스의 선언에 속해야합니다.  
  
 컴파일러는 유효한 XML인 태그를 모두 처리합니다. 다음과 같은 태그는 사용자 용 설명 문서에 자주 사용 되는 기능을 제공합니다.  
  
||||  
|-|-|-|  
|[\<c>](../ide/c-visual-cpp.md)|[\<code>](../ide/code-visual-cpp.md)|[\<example>](../ide/example-visual-cpp.md)|  
|[\<예외 >](../ide/exception-visual-cpp.md)1|[\<포함 >](../ide/include-visual-cpp.md)1|[\<list>](../ide/list-visual-cpp.md)|  
|[\<para>](../ide/para-visual-cpp.md)|[\<param >](../ide/param-visual-cpp.md)1|[\<paramref >](../ide/paramref-visual-cpp.md)1|  
|[\<사용 권한 >](../ide/permission-visual-cpp.md)1|[\<remarks>](../ide/remarks-visual-cpp.md)|[\<returns>](../ide/returns-visual-cpp.md)|  
|[\<참조 >](../ide/see-visual-cpp.md)1|[\<seealso >](../ide/seealso-visual-cpp.md)1|[\<summary>](../ide/summary-visual-cpp.md)|  
|[\<value>](../ide/value-visual-cpp.md)|||  
  
 1. 컴파일러 구문을 확인합니다.  
  
 현재 릴리스에서 Visual c + + 컴파일러 지원 하지 않습니다 `<paramref>`, 다른 Visual Studio 컴파일러에서 지원 되는 태그입니다. Visual c + + 지원할 수 있습니다 `<paramref>` 이후 릴리스에서 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)