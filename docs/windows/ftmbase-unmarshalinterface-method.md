---
title: "Ftmbase:: Unmarshalinterface 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce3710e84a9f7680b56f461029f279a659a5c14a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbaseunmarshalinterface-method"></a>FtmBase::UnmarshalInterface 메서드
새로 만든된 프록시를 초기화 하 고 해당 프록시에 대 한 인터페이스 포인터를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStm`  
 인터페이스 포인터를 마샬링해야 할는 스트림에 대 한 포인터입니다.  
  
 `riid`  
 마샬링해야 할 인터페이스의 식별자에 대 한 참조입니다.  
  
 `ppv`  
 이 작업이 완료 되 면에서 요청 된 인터페이스 포인터를 받는 포인터 변수의 주소 `riid`합니다. 이 작업은 성공 하는 경우 *`ppv` 마샬링해야 할 인터페이스의 요청 된 인터페이스 포인터를 포함 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않고 E_NOINTERFACE 또는 E_FAIL입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)