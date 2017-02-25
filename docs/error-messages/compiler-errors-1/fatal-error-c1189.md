---
title: "심각한 오류 C1189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1189"
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 심각한 오류 C1189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오류 번호: 사용자 제공 오류 메시지  
  
 C1189는 `#error` 지시문에 의해 생성됩니다.  이 지시문을 코딩하는 개발자는 오류 메시지의 텍스트를 지정합니다.  자세한 내용은 [\#error 지시문](../../preprocessor/hash-error-directive-c-cpp.md)을 참조하십시오.  
  
 다음 샘플에서는 C1189 오류가 발생하는 경우를 보여 줍니다.  이 샘플의 경우 `_WIN32` 식별자가 정의되어 있기 않기 때문에 개발자는 사용자 지정 오류 메시지를 표시합니다.  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 **\/robust** MIDL 컴파일러 옵션을 사용하여 ATL 프로젝트를 빌드하는 경우에도 이 오류를 볼 수 있습니다.  **\/robust** 빌드만 스위치 [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] 및 이후 버전의 Windows를 사용하세요.  다음 프로시저중 하나를 사용하여 이 오류를 해결합니다.  
  
-   dlldatax.c 파일에서 다음 줄을 변경합니다.  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 다음과 같이 변경합니다.  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   **MIDL** 속성 페이지 폴더에서 **고급** 속성 페이지를 사용하여 **\/robust** 스위치를 제거한 다음 **\/no\_robust** 스위치를 지정합니다.  자세한 내용은 [MIDL 속성 페이지: 고급](../../ide/midl-property-pages-advanced.md)을 참조하십시오.  
  
## 참고 항목  
 [\#define 지시문](../../preprocessor/hash-define-directive-c-cpp.md)