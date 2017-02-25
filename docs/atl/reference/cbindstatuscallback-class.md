---
title: "CBindStatusCallback Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBindStatusCallback"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "asynchronous data transfer [C++]"
  - "CBindStatusCallback class"
  - "data transfer [C++]"
  - "data transfer [C++], 비동기"
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CBindStatusCallback Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 `IBindStatusCallback` 인터페이스를 구현합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <class   
      T  
      , int   
      nBindFlags  
      = BINDF_ASYNCHRONOUS |   
BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx  
<T::_ThreadModel::ThreadModelNoCS>, public IBindStatusCallbackImpl<T>   
```  
  
#### 매개 변수  
 `T`  
 데이터를 수신할 때 호출 되는 함수를 포함 하는 클래스입니다.  
  
 *nBindFlags*  
 반환 되는 바인딩 플래그를 지정 합니다.  [GetBindInfo](../Topic/CBindStatusCallback::GetBindInfo.md).  기본 구현은 비동기 바인딩을 설정 데이터\/개체의 최신 버전을 검색 하 고 디스크 캐시에서 검색된 된 데이터를 저장 하지 않습니다.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CBindStatusCallback::CBindStatusCallback](../Topic/CBindStatusCallback::CBindStatusCallback.md)|생성자입니다.|  
|[CBindStatusCallback::~CBindStatusCallback](../Topic/CBindStatusCallback::~CBindStatusCallback.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CBindStatusCallback::Download](../Topic/CBindStatusCallback::Download.md)|다운로드 프로세스를 시작 하는 정적 메서드를 작성 한 `CBindStatusCallback` 개체를 호출 하 고 `StartAsyncDownload`.|  
|[CBindStatusCallback::GetBindInfo](../Topic/CBindStatusCallback::GetBindInfo.md)|비동기 모니커 만들어질 바인딩 요청 정보를 호출 합니다.|  
|[CBindStatusCallback::GetPriority](../Topic/CBindStatusCallback::GetPriority.md)|바인딩 작업의 우선 순위를 얻으려면 비동기 모니커에 의해 호출 됩니다.  ATL 구현을 반환 `E_NOTIMPL`.|  
|[CBindStatusCallback::OnDataAvailable](../Topic/CBindStatusCallback::OnDataAvailable.md)|대로 응용 프로그램에 데이터를 제공 하기 위해 호출 됩니다.  데이터를 읽는 다음 전달 하 여 데이터를 사용 하는 함수를 호출 합니다.|  
|[CBindStatusCallback::OnLowResource](../Topic/CBindStatusCallback::OnLowResource.md)|리소스가 부족 하면 호출 됩니다.  ATL 구현을 반환 `S_OK`.|  
|[CBindStatusCallback::OnObjectAvailable](../Topic/CBindStatusCallback::OnObjectAvailable.md)|비동기 모니커를 응용 프로그램 개체 인터페이스 포인터를 전달 하 여 호출 됩니다.  ATL 구현을 반환 `S_OK`.|  
|[CBindStatusCallback::OnProgress](../Topic/CBindStatusCallback::OnProgress.md)|데이터 다운로드 프로세스의 진행률을 나타내기 위해 호출 됩니다.  ATL 구현을 반환 `S_OK`.|  
|[CBindStatusCallback::OnStartBinding](../Topic/CBindStatusCallback::OnStartBinding.md)|바인딩 시작 될 때 호출 됩니다.|  
|[CBindStatusCallback::OnStopBinding](../Topic/CBindStatusCallback::OnStopBinding.md)|비동기 데이터 전송을 중지할 때 호출 됩니다.|  
|[CBindStatusCallback::StartAsyncDownload](../Topic/CBindStatusCallback::StartAsyncDownload.md)|사용 가능한 바이트를 초기화 하 고 URL 및 호출에서 푸시 형 stream 개체 바이트 0으로 읽을 만듭니다 `OnDataAvailable` 때 데이터를 사용할 수 있습니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CBindStatusCallback::m\_dwAvailableToRead](../Topic/CBindStatusCallback::m_dwAvailableToRead.md)|읽을 수 있는 바이트 수입니다.|  
|[CBindStatusCallback::m\_dwTotalRead](../Topic/CBindStatusCallback::m_dwTotalRead.md)|총 바이트 수입니다.|  
|[CBindStatusCallback::m\_pFunc](../Topic/CBindStatusCallback::m_pFunc.md)|함수 포인터는 데이터를 사용할 수 있을 때 호출 됩니다.|  
|[CBindStatusCallback::m\_pT](../Topic/CBindStatusCallback::m_pT.md)|비동기 데이터 전송을 요청 하는 개체에 대 한 포인터입니다.|  
|[CBindStatusCallback::m\_spBindCtx](../Topic/CBindStatusCallback::m_spBindCtx.md)|포인터는  [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) 인터페이스에 대 한 현재 바인딩 작업.|  
|[CBindStatusCallback::m\_spBinding](../Topic/CBindStatusCallback::m_spBinding.md)|포인터는 `IBinding` 인터페이스에 대 한 현재 바인딩 작업.|  
|[CBindStatusCallback::m\_spMoniker](../Topic/CBindStatusCallback::m_spMoniker.md)|포인터는  [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) 인터페이스를 사용 하는 URL입니다.|  
|[CBindStatusCallback::m\_spStream](../Topic/CBindStatusCallback::m_spStream.md)|포인터는  [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 인터페이스에 대 한 데이터 전송.|  
  
## 설명  
 `CBindStatusCallback` 클래스는 `IBindStatusCallback` 인터페이스를 구현합니다.  `IBindStatusCallback`이 비동기 데이터 전송에서 알림을 받을 수 있도록 응용 프로그램에 의해 구현 되어야 합니다.  시스템에서 제공 하는 비동기 모니커를 사용 하 여 `IBindStatusCallback` 메서드는 비동기 데이터에 대 한 정보를 주고받을 수 전송 개체에서.  
  
 일반적으로 `CBindStatusCallback` 개체는 특정 바인딩 작업과 연결 합니다.  예를 들어,는  [비동기](../../top/visual-cpp-samples.md) 샘플 URL 속성을 설정 하는 경우이 만듭니다는 `CBindStatusCallback` 개체를 호출 하 여 `Download`.  
  
 [!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/CPP/cbindstatuscallback-class_1.h)]  
  
 비동기 모니커 콜백 함수를 사용 하 여 `OnData` 데이터가 있으면 응용 프로그램을 호출 합니다.  비동기 모니커는 시스템에 의해 제공 됩니다.  
  
## 상속 계층 구조  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)