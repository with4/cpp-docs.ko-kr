---
title: 프로그래밍 방식 인쇄 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a439080cec7f3ae96014e9df6ddc65782686bf0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="programmatic-printing"></a>프로그래밍 방식 인쇄
OLE 제공 영구 문서를 고유 하 게 식별 하는 방법 (**GetClassFile**) 연결 된 코드에 로드 하 고 (`CoCreateInstance`, **QueryInterface(IID_IPersistFile)**, **QueryInterface(IID_IPersistStorage)**, **IPersistFile::Load**, 및 **IPersistStorage::Load**). 인쇄 문서를 더 이상 사용 하려면 (원래 OLE 2.0 함께 제공 되지 않으며 기존 OLE 디자인 사용) 하는 액티브 문서 포함 소개 자료 표준 인쇄 인터페이스 `IPrint`, 일반적으로 로드할 수 있는 모든 개체를 통해 사용할 수는 문서 종류의 영구 상태입니다. 현재 문서의 각 보기 필요에 따라 지원할 수는 **IPrint** 이러한 기능을 제공 하는 인터페이스입니다.  
  
 `IPrint` 인터페이스는 다음과 같이 정의 됩니다.  
  
```  
interface IPrint : IUnknown  
    {  
    HRESULT SetInitialPageNum([in] LONG nFirstPage);  
    HRESULT GetPageInfo(  
        [out] LONG *pnFirstPage,  
        [out] LONG *pcPages);  
    HRESULT Print(  
        [in] DWORD grfFlags,  
        [in,out] DVTARGETDEVICE **pptd,  
        [in,out] PAGESET ** ppPageSet,  
        [in,out] STGMEDIUM **ppstgmOptions,  
        [in] IContinueCallback* pCallback,  
        [in] LONG nFirstPage,  
        [out] LONG *pcPagesPrinted,  
        [out] LONG *pnPageLast);  
    };  
```  
  
 클라이언트와 컨테이너를 사용 하면 **IPrint::Print** 에 대 한 문서를 인쇄 하려면 페이지, 대상 장치, 인쇄 컨트롤 플래그를 지정 하는 문서를 로드할 인쇄 명령 및 추가 옵션입니다. 클라이언트 인터페이스를 통해 인쇄 연속 제어할 수도 `IContinueCallback` (아래 참조).  
  
 또한 **IPrint::SetInitialPageNum** 번호 매기기 하 여 페이지를 원활 하 게 분명 Office Binder와 같은 액티브 문서 컨테이너에 대 한 혜택으로 일련의 문서를 인쇄 하는 기능을 지원 합니다. **IPrint::GetPageInfo** 시작을 검색 하는 호출자를 허용 하 여 간단한 페이지 매김 정보를 표시 하면 페이지에 이전에 전달 된 번호 **SetInitialPageNum** (또는 내부 기본 문서 시작 페이지 번호)와 문서에는 페이지 수입니다.  
  
 개체를 지 원하는 `IPrint` 레지스트리에 저장 된 개체의 CLSID "Printable" 키로 표시 됩니다.  
  
 HKEY_CLASSES_ROOT\CLSID\\{...} \Printable  
  
 `IPrint` 일반적으로 지 원하는 동일한 개체에 구현 `IPersistFile` 또는 `IPersistStorage`합니다. 호출자가 프로그래밍 방식으로 "인쇄 가능" 키에 대 한 레지스트리를 확인 하 여 일부 클래스의 영구 상태를 인쇄 하는 기능을 확인 합니다. 현재는 "인쇄 가능"에 대 한 지원 이상의 나타냅니다 `IPrint`; 다른 인터페이스 정의 될 수 있습니다 나중에 다음 사용할 수를 통해 `QueryInterface` 여기서 **IPrint** 단순히 기본 수준의 지원 나타냅니다.  
  
 인쇄 절차 중 클라이언트 또는 인쇄 계속할지 여부를 제어 하는 인쇄를 시작 하는 컨테이너를 할 수 있습니다. 예를 들어 컨테이너에는 인쇄 작업을 가능한 한 빨리 종료 해야 하는 "중지 Print" 명령을 지원할 수 있습니다. 이 기능을 지원 하려면 클라이언트 인쇄 가능한 개체의 인터페이스와 작은 알림 싱크 개체가 구현할 수 `IContinueCallback`:  
  
```  
interface IContinueCallback : IUnknown  
    {  
    HRESULT FContinue(void);  
    HRESULT FContinuePrinting(  
        [in] LONG cPagesPrinted,  
        [in] LONG nCurrentPage,  
        [in] LPOLESTR pszPrintStatus);  
    };  
```  
  
 이 인터페이스는 Win32 API의 다양 한 연속 절차를 대신 하는 제네릭 연속 콜백 함수도 유용 하도록 설계 되었습니다 (같은 **AbortProc** 인쇄용 및  **EnumMetafileProc** 메타 파일 열거형에 대 한). 따라서이 인터페이스 디자인에 시간이 많이 걸리는 프로세스의 다양 한 유용합니다.  
  
 가장 일반적인 경우에는 **IContinueCallback::FContinue** 긴 프로세스에 의해 함수를 주기적으로 호출 합니다. 싱크 개체가 반환 `S_OK` 는 작업을 계속할 수 및 **S_FALSE** 를 가능한 한 빨리 프로시저를 중지 합니다.  
  
 **그러나 FContinue**,의 컨텍스트에서 사용 되지 않습니다 됩니다 **IPrint::Print**; 대신 사용 하 여 인쇄 **IContinueCallback::FContinuePrint**합니다. 모든 인쇄 개체를 주기적으로 호출 해야 **FContinuePrinting** 인쇄 된 페이지 수, 인쇄 중인 페이지 번호 및 클라이언트 수는 인쇄 상태를 설명 하는 추가 문자열을 전달 사용자 (예: "5 페이지는 19")을 표시 하려면 선택 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [액티브 문서 컨테이너](../mfc/active-document-containers.md)

