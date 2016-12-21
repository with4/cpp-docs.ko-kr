---
title: "IRunnableObjectImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IRunnableObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨테이너, running controls"
  - "컨트롤[ATL], 실행"
  - "컨트롤[C++], container running in ATL"
  - "IRunnableObject, ATL 구현"
  - "IRunnableObjectImpl class"
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRunnableObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 구현 합니다.  **IUnknown** 의 기본 구현을 제공 하 고 있는  [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) 인터페이스.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template< class   
      T  
      >  
class IRunnableObjectImpl  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IRunnableObjectImpl`.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IRunnableObjectImpl::GetRunningClass](../Topic/IRunnableObjectImpl::GetRunningClass.md)|실행 중인 컨트롤의 CLSID를 반환합니다.  CLSID ATL 구현 집합 `GUID_NULL` 를 반환 하 고  **E\_UNEXPECTED**.|  
|[IRunnableObjectImpl::IsRunning](../Topic/IRunnableObjectImpl::IsRunning.md)|컨트롤이 실행 되 고 있는지 확인 합니다.  ATL 구현을 반환  **TRUE**.|  
|[IRunnableObjectImpl::LockRunning](../Topic/IRunnableObjectImpl::LockRunning.md)|실행 중인 상태로 컨트롤을 잠급니다.  ATL 구현을 반환 `S_OK`.|  
|[IRunnableObjectImpl::Run](../Topic/IRunnableObjectImpl::Run.md)|실행 하도록 강제로 합니다.  ATL 구현을 반환 `S_OK`.|  
|[IRunnableObjectImpl::SetContainedObject](../Topic/IRunnableObjectImpl::SetContainedObject.md)|컨트롤에 포함 되어 있음을 나타냅니다.  ATL 구현을 반환 `S_OK`.|  
  
## 설명  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) 인터페이스 컨테이너 컨트롤이 실행 되 고 있는지 확인 하 고 강제로 실행 또는 실행 중인 상태로 잠글 수 있습니다.  클래스 `IRunnableObjectImpl` 는이 인터페이스의 기본 구현을 제공 하 고 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)