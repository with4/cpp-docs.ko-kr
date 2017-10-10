---
title: "심각한 오류 C1189 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6e8d3c9ff44a436688accfe267141390d23c0eb5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1189"></a>심각한 오류 C1189
\#오류: 사용자가 제공한 오류 메시지  
  
 C1189에서 생성 되는 `#error` 지시문입니다. 지시문을 코딩 하는 개발자는 오류 메시지의 텍스트를 지정 합니다. 자세한 내용은 참조 [#error 지시문 (C/c + +)](../../preprocessor/hash-error-directive-c-cpp.md)합니다.  
  
 다음 샘플에서는 C1189 오류가 발생 합니다. 이 샘플에서는 개발자는 사용자 지정 오류 메시지를 때문에 `_WIN32` 식별자에 정의 되어 있지 않습니다.  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 ATL 프로젝트를 사용 하 여 작성 하는 경우에이 오류가 표시 될 수 있습니다는 **/robust** MIDL 컴파일러 옵션입니다. 사용 하 여는 **/robust** 스위치만 빌드를 [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] 및 이후 버전의 Windows 합니다. 이 오류를 해결하려면 다음 절차 중 하나를 사용합니다.  
  
-   Dlldatax.c 파일에서이 줄을 변경 합니다.  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 다음과 같이 변경합니다.  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   사용 하 여는 **고급** 속성 페이지에는 **MIDL** 속성 페이지 폴더를 제거 하는 **/robust** 전환한 다음 지정는 **/no_robust** 전환 합니다. 자세한 내용은 참조 [MIDL 속성 페이지: 고급](../../ide/midl-property-pages-advanced.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [#define 지시문(C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
