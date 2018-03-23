---
title: FtmBase 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
dev_langs:
- C++
helpviewer_keywords:
- FtmBase class
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9499a5a30f99e639137532aad1763b434a196809
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="ftmbase-class"></a>FtmBase 클래스
자유 스레드된 마샬러 개체를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,   
   Microsoft::WRL::CloakedIid<IMarshal> >;  
```  
  
## <a name="remarks"></a>설명  
 자세한 내용은 MSDN Library에서 "COM 참조" 항목의 "COM 인터페이스" 하위 항목인 "IMarshal" 항목을 참조 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[FtmBase::FtmBase 생성자](../windows/ftmbase-ftmbase-constructor.md)|FtmBase 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[FtmBase::CreateGlobalInterfaceTable 메서드](../windows/ftmbase-createglobalinterfacetable-method.md)|(GIT) 전역 인터페이스 테이블을 만듭니다.|  
|[FtmBase::DisconnectObject 메서드](../windows/ftmbase-disconnectobject-method.md)|개체에 대 한 모든 외부 연결을 강제로 해제합니다. 개체의 서버를 종료 하기 전에이 메서드는 개체의 구현을 호출 합니다.|  
|[FtmBase::GetMarshalSizeMax 메서드](../windows/ftmbase-getmarshalsizemax-method.md)|지정된 된 개체에 지정 된 인터페이스 포인터를 마샬링하는 데 필요한 바이트 수의 상한 값을 가져옵니다.|  
|[FtmBase::GetUnmarshalClass 메서드](../windows/ftmbase-getunmarshalclass-method.md)|COM 해당 프록시에 대 한 코드를 포함 하는 DLL을 찾기 위해 사용 하는 CLSID를 가져옵니다. COM 프록시 초기화 되지 않은 인스턴스를 만들려면이 DLL을 로드 합니다.|  
|[FtmBase::MarshalInterface 메서드](../windows/ftmbase-marshalinterface-method.md)|특정 클라이언트 프로세스에서 프록시 개체를 초기화 하는 데 필요한 데이터를 스트림으로 씁니다.|  
|[FtmBase::ReleaseMarshalData 메서드](../windows/ftmbase-releasemarshaldata-method.md)|마샬링된 데이터 패킷을 소멸 시킵니다.|  
|[FtmBase::UnmarshalInterface 메서드](../windows/ftmbase-unmarshalinterface-method.md)|새로 만든된 프록시를 초기화 하 고 해당 프록시에 대 한 인터페이스 포인터를 반환 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[FtmBase::marshaller_ 데이터 멤버](../windows/ftmbase-marshaller-data-member.md)|자유 스레드된 마샬러에 대 한 참조를 보유합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `FtmBase`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)