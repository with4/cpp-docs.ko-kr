---
title: "FtmBase 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FtmBase 클래스"
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

자유 스레드된 마샬러 개체를 나타냅니다.  
  
## 구문  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags< WinRtClassicComMix >,   
   Microsoft::WRL::CloakedIid< IMarshal > >;  
```  
  
## 설명  
 자세한 내용은 MSDN Library에서 "COM 참조" 항목의 "COM 인터페이스" 하위의 "IMarshal" 항목을 참조 하십시오.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[FtmBase::FtmBase 생성자](../windows/ftmbase-ftmbase-constructor.md)|Ftm 기본 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[FtmBase::CreateGlobalInterfaceTable 메서드](../windows/ftmbase-createglobalinterfacetable-method.md)|전역 인터페이스 테이블 \(GIT\)를 만듭니다.|  
|[FtmBase::DisconnectObject 메서드](../windows/ftmbase-disconnectobject-method.md)|개체에 대한 모든 외부 연결을 강제로 해제합니다.  개체의 서버 개체의 구현을 종료하기 전에, 이 메서드를 호출 합니다.|  
|[FtmBase::GetMarshalSizeMax 메서드](../windows/ftmbase-getmarshalsizemax-method.md)|지정된 된 개체에서 지정된 인터페이스 포인터를 마샬링하는 데 필요한 바이트의 수에 상한을 가져옵니다.|  
|[FtmBase::GetUnmarshalClass 메서드](../windows/ftmbase-getunmarshalclass-method.md)|COM 해당 프록시에 대한 코드를 포함하는 DLL을 찾기 위해 사용하는 CLSID를 가져옵니다.  COM 프록시의 초기화되지 않은 인스턴스를 만들고, 이 DLL을 로드 합니다.|  
|[FtmBase::MarshalInterface 메서드](../windows/ftmbase-marshalinterface-method.md)|일부 클라이언트 프로세스에서 프록시 개체를 초기화하는 데 필요한 데이터를 스트림으로 씁니다.|  
|[FtmBase::ReleaseMarshalData 메서드](../windows/ftmbase-releasemarshaldata-method.md)|마샬링된 데이터 패킷을 소멸시킵니다.|  
|[FtmBase::UnmarshalInterface 메서드](../windows/ftmbase-unmarshalinterface-method.md)|새로 생성된 프록시를 초기화하고 해당 프록시에 대한 인터페이스 포인터를 반환합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[FtmBase::marshaller\_ 데이터 멤버](../windows/ftmbase-marshaller-data-member.md)|자유 스레드된 마샬러에 대한 참조를 보유합니다.|  
  
## 상속 계층  
 `FtmBase`  
  
## 요구 사항  
 **헤더:**  ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)