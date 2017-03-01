---
title: "AFX_EXTENSION_MODULE 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: f2699316266e9cc061fa898c4176e36ae8323b33
ms.lasthandoff: 02/24/2017

---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE 구조체
`AFX_EXTENSION_MODULE` MFC 확장 Dll 초기화 하는 동안 확장 DLL 모듈의 상태를 저장 하는 데 사용 됩니다.  
  
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
 DLL 모듈의 핸들을 지정합니다.  
  
 *hResource*  
 DLL 사용자 지정 리소스 모듈의 핸들을 지정합니다.  
  
 *pFirstSharedClass*  
 정보에 대 한 포인터 (의 `CRuntimeClass` 구조) DLL 모듈의 첫 번째 런타임 클래스에 대 한 합니다. 런타임 클래스 목록의 시작 부분을 제공 하는 데 사용 합니다.  
  
 *pFirstSharedFactory*  
 DLL 모듈의 첫 번째 개체 팩터리에 대 한 포인터 (한 `COleObjectFactory` 개체). 클래스 팩터리 목록의 시작 부분을 제공 하는 데 사용 합니다.  
  
## <a name="remarks"></a>주의  
 MFC 확장 Dll의 두 가지를 수행 해야 자신의 `DllMain` 함수:  
  
-   호출 [AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1) 반환 값을 확인 합니다.  
  
-   만들기는 **CDynLinkLibrary** DLL를 내보내는 경우 개체 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체, 한 고유한 사용자 지정 리소스입니다.  
  
 `AFX_EXTENSION_MODULE` 구조는 DLL 모듈 상태를 일반 정적 개체가 생성 되기 전에 실행의 일부로 확장 DLL 초기화 된 후 런타임 클래스 개체의 복사본을 포함 하 여 확장의 복사본을 저장 하는 데 사용 됩니다 `DllMain` 를 입력 합니다. 예:  
  
 [!code-cpp[NVC_MFC_DLL&#2;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 에 저장 된 모듈 정보는 `AFX_EXTENSION_MODULE` 구조를 복사할 수는 **CDynLinkLibrary** 개체입니다. 예:  
  
 [!code-cpp[NVC_MFC_DLL&#5;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1)   
 [AfxTermExtensionModule](http://msdn.microsoft.com/library/b64de402-f1e3-4c26-9823-08c07876aaaa)


