---
title: "HSE_VERSION_INFO 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HSE_VERSION_INFO
dev_langs:
- C++
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 78b1ed79093db179e00f262b61934ff9c293ff18
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="hseversioninfo-structure"></a>HSE_VERSION_INFO 구조체
이 구조에 의해 지정 된 `pVer` 에서 매개 변수는 `CHttpServer::GetExtensionVersion` 멤버 함수입니다. ISA 버전 번호 및는 ISA.에 대 한 텍스트 설명을 제공합니다  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _HSE_VERSION_INFO {  
    DWORD dwExtensionVersion;  
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *dwExtensionVersion*  
 ISA.의 버전 번호  
  
 *lpszExtensionDesc*  
 ISA.의 텍스트 설명 기본 구현은 개체 틀 텍스트를 제공합니다. 재정의 `CHttpServer::GetExtensionVersion` 고유한 설명을 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** httpext.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


