---
title: "HSE_VERSION_INFO 구조체 | Microsoft Docs"
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
  - "HSE_VERSION_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HSE_VERSION_INFO 구조체"
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HSE_VERSION_INFO 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

This structure is pointed to by the `pVer` parameter in the `CHttpServer::GetExtensionVersion` member function.  It provides the ISA version number and a text description of the ISA.  
  
## 구문  
  
```  
  
      typedef struct _HSE_VERSION_INFO {  
   DWORD dwExtensionVersion;  
   CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### 매개 변수  
 *dwExtensionVersion*  
 The version number of the ISA.  
  
 *lpszExtensionDesc*  
 The text description of the ISA.  The default implementation provides placeholder text; override `CHttpServer::GetExtensionVersion` to provide your own description.  
  
## 요구 사항  
 **Header:** httpext.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)