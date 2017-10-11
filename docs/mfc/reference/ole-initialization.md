---
title: "OLE 초기화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: d86083701e6fb0510eb0fa79f0812fca95445881
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="ole-initialization"></a>OLE 초기화
응용 프로그램 OLE 시스템 서비스를 사용 하려면 먼저 OLE 시스템 Dll을 초기화 하 고 Dll은 올바른 버전 인지 확인 해야 하기. **AfxOleInit** 함수 OLE 시스템 Dll을 초기화 합니다.  
  
### <a name="ole-initialization"></a>OLE 초기화  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|OLE 라이브러리를 초기화합니다.| 
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|응용 프로그램 개체에서이 함수를 호출 `InitInstance` 함수 OLE 컨트롤의 포함에 대 한 지원을 사용 하도록 설정 합니다.| 


## <a name="afxenablecontrolcontainer"></a>AfxEnableControlContainer
응용 프로그램 개체에서이 함수를 호출 `InitInstance` 함수 OLE 컨트롤의 포함에 대 한 지원을 사용 하도록 설정 합니다.  
   
### <a name="syntax"></a>구문    
```
void AfxEnableControlContainer( );  
```  
   
### <a name="remarks"></a>설명  
 OLE 컨트롤 (이제 ActiveX 컨트롤 이라고 함)에 대 한 자세한 내용은 참조 하십시오. [ActiveX 컨트롤 항목](../mfc-activex-controls.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  

  
##  <a name="afxoleinit"></a>AfxOleInit  
 OLE 지원을 응용 프로그램에 대 한 초기화합니다.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 초기화에 실패 하면 수 있는 잘못 된 버전의 OLE 시스템 Dll이 설치 되어 있는 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 MFC 응용 프로그램에 대 한 OLE 지원을 초기화 하기 위해이 함수를 호출 합니다. 이 함수를 호출할 때 다음 작업이 수행 됩니다.  
  
-   호출 응용 프로그램의 현재 아파트에 COM 라이브러리를 초기화합니다. 자세한 내용은 참조 [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134)합니다.  
  
-   메시지 필터 개체를 만들고 구현 하는 [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740) 인터페이스입니다. 이 메시지 필터를 호출 하 여 액세스할 수 [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)합니다.  
  
> [!NOTE]
>  경우 **AfxOleInit** 호출 되는 MFC DLL에서 호출이 실패 합니다. 오류 함수, DLL에서 호출 되 면 OLE 시스템 이전에 초기화 된 호출 응용 프로그램에 의해 가정 하기 때문에 발생 합니다.  
  
> [!NOTE]
>  MFC 응용 프로그램은 단일 스레드 아파트 (STA)으로 초기화 되어야 합니다. 호출 하는 경우 [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) 에 프로그램 `InitInstance` 재정의 지정 `COINIT_APARTMENTTHREADED` (대신 `COINIT_MULTITHREADED`). 자세한 내용은 참조 PRB: MFC 응용 프로그램이 다른 이름으로 다중 스레드 아파트 (828643)에서 응용 프로그램을 초기화 하는 경우 응답 하지 [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

