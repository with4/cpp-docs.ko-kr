---
title: 'Ftmbase:: Getunmarshalclass 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs:
- C++
helpviewer_keywords:
- GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 09afd9f977dbc779eb1dc10e9553d2ca88538fcc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="ftmbasegetunmarshalclass-method"></a>FtmBase::GetUnmarshalClass 메서드
COM 해당 프록시에 대 한 코드를 포함 하는 DLL을 찾기 위해 사용 하는 CLSID를 가져옵니다. COM 프록시 초기화 되지 않은 인스턴스를 만들려면이 DLL을 로드 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 마샬링해야 하는 인터페이스의 식별자에 대 한 참조입니다.  
  
 `pv`  
 마샬링할; 인터페이스에 대 한 포인터 호출자는 원하는 인터페이스에 대 한 포인터 없는 경우 NULL이 될 수 있습니다.  
  
 `dwDestContext`  
 대상 컨텍스트 마샬링해야 할 지정된 된 인터페이스입니다.  
  
 하나 이상의 MSHCTX 열거형 값을 지정 합니다.  
  
 역마샬링 (MSHCTX_INPROC) 현재 프로세스의 다른 아파트에서 또는 현재 프로세스 (MSHCTX_LOCAL)와 같은 컴퓨터에 다른 프로세스에서 발생할 수 있습니다.  
  
 `pvDestContext`  
 나중에 사용 됩니다. NULL 이어야 합니다.  
  
 `mshlflags`  
 이 작업이 완료 될 때, 클라이언트 프로세스에서 프록시를 만드는 데 사용할 CLSID에 대 한 포인터입니다.  
  
 `pCid`  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 이렇게 하지 않으면 S_FALSE입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)