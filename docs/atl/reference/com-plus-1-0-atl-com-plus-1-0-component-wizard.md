---
title: "COM+ 1.0, ATL COM+ 1.0 구성 요소 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.mts.options"
dev_langs: 
  - "C++"
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM+ 1.0, ATL COM+ 1.0 구성 요소 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL COM\+ 1.0 구성 요소 마법사의 이 페이지에서는 지원될 인터페이스 형식과 추가 인터페이스를 지정합니다.  
  
 ATL 프로젝트 및 ATL COM 클래스에 대한 자세한 내용은 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)를 참조하십시오.  
  
 **Interface**  
 개체에서 지원하는 인터페이스 형식을 나타냅니다.  기본적으로 개체에서는 이중 인터페이스를 지원합니다.  
  
|옵션|설명|  
|--------|--------|  
|**이중**|개체에서 이중 인터페이스를 지원하도록 지정합니다. 이 인터페이스의 vtable에는 사용자 지정 인터페이스 함수와 런타임 시 바인딩 `IDispatch` 메서드가 있습니다.  이중 인터페이스를 사용하면 COM 클라이언트와 자동화 컨트롤러 모두 개체에 액세스할 수 있습니다.|  
|**사용자 지정**|개체에서 사용자 지정 인터페이스를 지원하도록 지정합니다. 이 인터페이스의 vtable에는 사용자 지정 인터페이스 함수가 있습니다.  사용자 지정 인터페이스는 특히 프로세스 경계에서 이중 인터페이스보다 더 빠를 수 있습니다.<br /><br /> -   **자동화 호환** 사용자 지정 인터페이스에 자동화 지원을 추가 합니다.  특성을 사용하는 프로젝트의 경우 coclass에서 **oleautomation** 특성을 설정합니다.|  
  
 **큐 사용 가능**  
 클라이언트에서 메시지 큐를 사용하여 비동기로 이 구성 요소를 호출할 수 있음을 나타냅니다.  매크로 사용자 지정으로 특성을 사용하는 구성 요소\(TLBATTR\_QUEUEABLE, 0\)를 .h 파일\(특성을 사용하는 프로젝트\)이나 .idl 파일\(특성을 사용하지 않는 프로젝트\)에 추가합니다.  
  
 **지원**  
 오류 처리 및 개체 컨트롤에 대한 추가 지원을 나타냅니다.  
  
|옵션|설명|  
|--------|--------|  
|**ISupportErrorInfo**|[ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) 인터페이스에 대한 지원을 제공하여 개체에서 클라이언트로 오류 정보를 반환할 수 있도록 합니다.|  
|**IObjectControl**|개체에서 세 가지 [IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474) 메서드, 즉 [Activate](http://msdn.microsoft.com/library/windows/desktop/ms681303), [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322) 및 [Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms687094)에 액세스할 수 있게 합니다.|  
|**IObjectConstruct**|[IObjectConstruct](http://msdn.microsoft.com/library/windows/desktop/ms680583) 인터페이스에 대한 지원을 제공하여 다른 메서드나 개체로부터 수행되는 매개 변수 전달 작업을 관리합니다.|  
  
 **트랜잭션**  
 개체에서 트랜잭션을 지원하도록 지정합니다.  .idl 파일\(특성을 사용하지 않는 프로젝트\)에 mtxattr.h 파일을 포함시킵니다.  
  
|옵션|설명|  
|--------|--------|  
|**지원됨**|매크로 사용자 지정으로 특성을 사용하는 구성 요소\(TLBATTR\_TRANS\_SUPPORTED,0\)를 .h 파일\(특성을 사용하는 프로젝트\)이나 .idl 파일\(특성을 사용하지 않는 프로젝트\)에 추가하여 개체가 트랜잭션 스트림의 루트가 되지 않도록 지정합니다.|  
|**필수**|매크로 사용자 지정으로 특성을 사용하는 구성 요소\(TLBATTR\_TRANS\_REQUIRED,0\)를 .h 파일\(특성을 사용하는 프로젝트\)이나 .idl 파일\(특성을 사용하지 않는 프로젝트\)에 추가하여 개체가 트랜잭션 스트림의 루트가 되거나 되지 않도록 지정합니다.|  
|**지원 안 함**|개체에서 트랜잭션을 제외시키도록 지정합니다.  매크로 사용자 지정으로 특성을 사용하는 구성 요소\(TLBATTR\_TRANS\_NOTSUPP,0\)를 .h 파일\(특성을 사용하는 프로젝트\)이나 .idl 파일\(특성을 사용하지 않는 프로젝트\)에 추가합니다.|  
|**새 트랜잭션 필요**|매크로 사용자 지정으로 특성을 사용하는 구성 요소\(TLBATTR\_TRANS\_REQNEW,0\)를 .h 파일\(특성을 사용하는 프로젝트\)이나 .idl 파일\(특성을 사용하지 않는 프로젝트\)에 추가하여 개체가 항상 트랜잭션 스트림의 루트가 되도록 지정합니다.|  
  
## 참고 항목  
 [ATL COM\+ 1.0 구성 요소 마법사](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM\+ 1.0 Component](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)