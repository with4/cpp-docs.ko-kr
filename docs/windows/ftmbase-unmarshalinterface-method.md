---
title: 'Ftmbase:: Unmarshalinterface 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a1991454daa76fcf7878a7487080124b5a34dbeb
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644036"
---
# <a name="ftmbaseunmarshalinterface-method"></a>FtmBase::UnmarshalInterface 메서드
새로 만든된 프록시를 초기화 하 고 해당 프록시에 인터페이스 포인터를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pStm*  
 인터페이스 포인터를 역 마샬링해야 하는 스트림에 대 한 포인터입니다.  
  
 *riid*  
 역 마샬링해야 하는 인터페이스의 식별자에 대 한 참조입니다.  
  
 *ppv*  
 이 작업이 완료 되 면에서 요청 된 인터페이스 포인터를 받는 포인터 변수의 주소 *riid*합니다. 이 작업에 성공 하면 **ppv* 마샬링해야 하는 인터페이스의 요청 된 인터페이스 포인터를 포함 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 이 고, 그렇지 E_NOINTERFACE 또는 E_FAIL입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)