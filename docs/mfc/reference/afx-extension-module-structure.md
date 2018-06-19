---
title: AFX_EXTENSION_MODULE 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6560bf337f6e146bba19e41d56727945df771dd2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349260"
---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE 구조체
`AFX_EXTENSION_MODULE` MFC 확장 Dll의 초기화 동안 MFC 확장 DLL 모듈의 상태를 저장 하는 데 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct AFX_EXTENSION_MODULE  
{  
    BOOL bInitialized;  
    HMODULE hModule;  
    HMODULE hResource;  
    CRuntimeClass* pFirstSharedClass;  
    COleObjectFactory* pFirstSharedFactory;  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *bInitialized*  
 **True 이면** DLL 모듈으로 초기화 된 경우 `AfxInitExtensionModule`합니다.  
  
 `hModule`  
 DLL 모듈의 핸들을 지정 합니다.  
  
 *hResource*  
 DLL 사용자 지정 리소스 모듈의 핸들을 지정 합니다.  
  
 *pFirstSharedClass*  
 정보에 대 한 포인터 (의 `CRuntimeClass` 구조) DLL 모듈의 첫 번째 런타임 클래스에 대 한 합니다. 런타임 클래스 목록의 시작 부분을 제공 하는 데 사용 합니다.  
  
 *pFirstSharedFactory*  
 DLL 모듈의 첫 번째 개체 팩터리에 대 한 포인터 (한 `COleObjectFactory` 개체). 클래스 팩터리 목록의 시작 부분을 제공 하는 데 사용 합니다.  
  
## <a name="remarks"></a>설명  
 MFC 확장 Dll 두 가지를 수행 해야 자신의 `DllMain` 함수:  
  
-   호출 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) 반환 값을 확인 합니다.  
  
-   만들기는 **CDynLinkLibrary** DLL를 내보내는 경우 개체 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 자체 사용자 지정 리소스 또는 개체입니다.  
  
 `AFX_EXTENSION_MODULE` 구조는 MFC 확장 DLL 모듈 상태를 실행 하기 전에 일반적인 정적 개체 생성의 일부로 MFC 확장 DLL에서 초기화 된 런타임 클래스 개체의 복사본을 포함 하 여의 복사본을 저장 하는 데 사용 되 `DllMain` 은 입력합니다. 예를 들어:  
  
 [!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 에 저장 된 모듈 정보는 `AFX_EXTENSION_MODULE` 구조를 복사할 수는 **CDynLinkLibrary** 개체입니다. 예를 들어:  
  
 [!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)   
 [AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

