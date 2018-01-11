---
title: "TN064: ActiveX 컨트롤의 아파트 모델 스레딩 한다 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.controls.activex
dev_langs: C++
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07730d6c078dcc8fcd7ea1406f8cff6f665c9919
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064: ActiveX 컨트롤의 아파트 모델 스레딩
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 기술 노트에서는 아파트 모델 스레딩 ActiveX 컨트롤에서 사용 하는 방법에 설명 합니다. 아파트 모델 스레딩이 지원 된다는 Visual c + + 버전 4.2 이상에서 note 합니다.  
  
## <a name="what-is-apartment-model-threading"></a>아파트 모델 스레딩 하는 것이 무엇입니까  
 아파트 모델에는 다중 스레드 컨테이너 응용 프로그램 내에서 ActiveX 컨트롤과 같은 포함 된 개체를 지원 하기 위해 방법입니다. 응용 프로그램이 여러 스레드를 가질 수 있지만 하나의 "아파트에," 단 하나의 스레드에서 실행 되 포함된 된 개체의 각 인스턴스에 할당 됩니다. 즉, 모든 호출은 컨트롤의 인스턴스로 동일한 스레드에서 발생 합니다.  
  
 그러나 동일한 형식의 컨트롤의 서로 다른 인스턴스는 서로 다른 아파트에 할당할 수 있습니다. 따라서 공통 (예: 전역 또는 정적 데이터)에 있는 모든 데이터를 공유 하는 컨트롤의 여러 인스턴스가 경우이 공유 데이터에 대 한 액세스 임계 영역 등의 동기화 개체를 보호 해야 합니다.  
  
 아파트 모델 스레딩 대 한 자세한 내용은 참조 하십시오 [프로세스 및 스레드](http://msdn.microsoft.com/library/windows/desktop/ms684841) 에 *OLE Programmer's Reference*합니다.  
  
## <a name="why-support-apartment-model-threading"></a>아파트 모델 스레딩 지원 이유  
 아파트 모델 스레딩 지 원하는 컨트롤을 지 원하는 아파트 모델 다중 스레드 컨테이너 응용 프로그램에서 사용할 수 있습니다. 아파트 모델을 사용 하지 않도록 컨트롤을 사용할 수 있는 컨테이너의 잠재적인 집합은 제한 합니다.  
  
 아파트 모델을 사용 하는 것은 거의 또는 전혀 공유 데이터를가지고 있는 경우에 특히 대부분의 컨트롤에 대 한 쉬운 합니다.  
  
## <a name="protecting-shared-data"></a>공유 데이터 보호  
 컨트롤에는 공유 데이터를 사용 하는 경우 예: 정적 멤버 변수에 대 한 액세스 둘 이상의 스레드에서 같은 시간에 데이터를 수정 하지 못하도록 임계 섹션으로 데이터를 보호 해야 합니다. 이 용도로 임계를 설정 하려면 클래스의 정적 멤버 변수를 선언 `CCriticalSection` 컨트롤의 클래스에 있습니다. 사용 하 여는 `Lock` 및 **잠금 해제** 코드 공유 데이터에 액세스 하는 경우 중요 한이 섹션의 멤버 함수 개체입니다.  
  
 예를 들어 모든 인스턴스에서 공유 하는 문자열을 유지 해야 하는 컨트롤 클래스를 고려 합니다. 이 문자열 정적 멤버 변수에서 유지 관리 하 고 임계 영역 보호 될 수 있습니다. 컨트롤의 클래스 선언을 다음이 포함 됩니다.  
  
```  
class CSampleCtrl : public COleControl  
{  
 ...  
    static CString _strShared;  
    static CCriticalSection _critSect;  
};  
```  
  
 클래스에 대 한 구현을이 변수들에 대 한 정의가 포함 됩니다.  
  
```  
int CString CSampleCtrl::_strShared;  
CCriticalSection CSampleCtrl::_critSect;  
```  
  
 에 대 한 액세스는 `_strShared` 정적 멤버 임계 영역으로 보호할 수 있습니다.  
  
```  
void CSampleCtrl::SomeMethod()  
{  
    _critSect.Lock();
if (_strShared.Empty())  
    _strShared = "<text>";  
    _critSect.Unlock();

 ...  
}  
```  
  
## <a name="registering-an-apartment-model-aware-control"></a>아파트 모델 인식 컨트롤 등록  
 아파트 모델 스레딩 지 원하는 컨트롤을 나타내야 레지스트리에서이 기능은 "ThreadingModel" 명명된 된 값을 추가 하 여 아래에 해당 클래스 ID 레지스트리 항목의 "Apartment"의 값이 있는 *클래스 id* \\ **InprocServer32** 키입니다. 이 컨트롤에 대해 자동으로 등록 될이 키를 전달 된 `afxRegApartmentThreading` 여섯 번째 매개 변수에서 플래그 `AfxOleRegisterControlClass`:  
  
```  
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)  
{  
    if (bRegister)  
    return AfxOleRegisterControlClass(
    AfxGetInstanceHandle(), 
    m_clsid, 
    m_lpszProgID, 
    IDS_SAMPLE, 
    IDB_SAMPLE, 
    afxRegApartmentThreading, 
    _dwSampleOleMisc, 
    _tlid, 
    _wVerMajor, 
    _wVerMinor);

 else  
    return AfxOleUnregisterClass(m_clsid,
    m_lpszProgID);

}  
```  
  
 컨트롤 프로젝트는 Visual c + + 버전 4.1 이상 컨트롤에서 생성 되었으면,이 플래그가 이미 코드에 표시 됩니다. 변경 하지 스레딩 모델을 등록 하는 데 필요한 됩니다.  
  
 프로젝트의 컨트롤은 이전 버전에서 생성 된 경우 기존 코드 여섯 번째 매개 변수로 부울 값을 갖습니다. 기존 매개 변수가 TRUE 인 경우 변경 `afxRegInsertable | afxRegApartmentThreading`합니다. 기존 매개 변수가 FALSE 인 경우 변경 `afxRegApartmentThreading`합니다.  
  
 컨트롤이 아파트 모델 스레딩에 대 한 규칙을 따르지 않으면 전달 하면 안 `afxRegApartmentThreading` 에이 매개 변수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

