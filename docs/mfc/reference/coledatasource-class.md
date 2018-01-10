---
title: "COleDataSource 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDataSource
- AFXOLE/COleDataSource
- AFXOLE/COleDataSource::COleDataSource
- AFXOLE/COleDataSource::CacheData
- AFXOLE/COleDataSource::CacheGlobalData
- AFXOLE/COleDataSource::DelayRenderData
- AFXOLE/COleDataSource::DelayRenderFileData
- AFXOLE/COleDataSource::DelaySetData
- AFXOLE/COleDataSource::DoDragDrop
- AFXOLE/COleDataSource::Empty
- AFXOLE/COleDataSource::FlushClipboard
- AFXOLE/COleDataSource::GetClipboardOwner
- AFXOLE/COleDataSource::OnRenderData
- AFXOLE/COleDataSource::OnRenderFileData
- AFXOLE/COleDataSource::OnRenderGlobalData
- AFXOLE/COleDataSource::OnSetData
- AFXOLE/COleDataSource::SetClipboard
dev_langs: C++
helpviewer_keywords:
- COleDataSource [MFC], COleDataSource
- COleDataSource [MFC], CacheData
- COleDataSource [MFC], CacheGlobalData
- COleDataSource [MFC], DelayRenderData
- COleDataSource [MFC], DelayRenderFileData
- COleDataSource [MFC], DelaySetData
- COleDataSource [MFC], DoDragDrop
- COleDataSource [MFC], Empty
- COleDataSource [MFC], FlushClipboard
- COleDataSource [MFC], GetClipboardOwner
- COleDataSource [MFC], OnRenderData
- COleDataSource [MFC], OnRenderFileData
- COleDataSource [MFC], OnRenderGlobalData
- COleDataSource [MFC], OnSetData
- COleDataSource [MFC], SetClipboard
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ce9abdccba549e0b0fd3c55bfb7fbaee6a11e27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="coledatasource-class"></a>COleDataSource 클래스
응용 프로그램이 데이터를 넣어 두었다 클립보드 또는 끌어 놓기 작업과 같은 데이터 전송 작업에서 해당 데이터를 제공하는 캐시의 역할을 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDataSource::COleDataSource](#coledatasource)|`COleDataSource` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDataSource::CacheData](#cachedata)|데이터를 사용 하 여 지정 된 형식에 제공 된 **STGMEDIUM** 구조입니다.|  
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|사용 하 여 지정 된 형식에서 데이터를 제공는 `HGLOBAL`합니다.|  
|[COleDataSource::DelayRenderData](#delayrenderdata)|지연 된 렌더링을 사용 하 여 지정 된 형식으로 데이터를에서 제공 합니다.|  
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|지정 된 형식에서 데이터를 제공는 `CFile` 포인터입니다.|  
|[COleDataSource::DelaySetData](#delaysetdata)|지원 되는 모든 형식에 대해 호출 `OnSetData`합니다.|  
|[Coledatasource:: Dodragdrop](#dodragdrop)|데이터 소스와 끌어서 놓기 작업을 수행 합니다.|  
|[COleDataSource::Empty](#empty)|비웁니다는 `COleDataSource` 데이터의 개체입니다.|  
|[COleDataSource::FlushClipboard](#flushclipboard)|모든 데이터를 클립보드에 렌더링합니다.|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|클립보드에 데이터 아직 중지 되지 않은 인지 확인 합니다.|  
|[COleDataSource::OnRenderData](#onrenderdata)|지연 된 렌더링의 일환으로 데이터를 검색합니다.|  
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|데이터를 검색 한 `CFile` 지연 된 렌더링의 일환으로 합니다.|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|데이터를 검색 한 `HGLOBAL` 지연 된 렌더링의 일환으로 합니다.|  
|[COleDataSource::OnSetData](#onsetdata)|데이터를 교체 하기 위해 호출 됩니다는 `COleDataSource` 개체입니다.|  
|[COleDataSource::SetClipboard](#setclipboard)|위치는 `COleDataSource` 개체 클립보드에 복사 합니다.|  
  
## <a name="remarks"></a>설명  
 OLE 데이터 소스를 직접 만들 수 있습니다. 또는 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 및 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 클래스에 대 한 응답에서 OLE 데이터 원본을 만들고 해당 `CopyToClipboard` 및 `DoDragDrop` 멤버 함수입니다. 참조 [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) 간략 한 설명에 대 한 합니다. 재정의 `OnGetClipboardData` OLE 데이터 원본의 데이터 추가 클립보드 형식을 추가 하 고 클라이언트 항목이 나 서버 항목 클래스의 멤버 함수에 대해 생성 된 `CopyToClipboard` 또는 `DoDragDrop` 멤버 함수입니다.  
  
 전송에 대 한 데이터를 준비 하려는 경우이 클래스의 개체 만들고 데이터에 가장 적합 한 방법을 사용 하 여 데이터를 입력 해야 합니다. 데이터 소스에 삽입 하는 방법은 직접 영향을 받는 데이터를 즉시 제공 했는지 여부를 (즉시 렌더링) 또는 요청 시 (지연 된 렌더링). 제공 하는 데이터에 사용할 클립보드 형식을 전달 하 여 모든 클립보드 형식에 대 한 (선택적 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조)를 호출 [DelayRenderData](#delayrenderdata)합니다.  
  
 데이터 원본 및 데이터 전송에 대 한 자세한 내용은 문서 참조 [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md)합니다. 또한 문서 [클립보드 항목](../../mfc/clipboard.md) OLE 클립보드 메커니즘을 설명 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="cachedata"></a>COleDataSource::CacheData  
 데이터는 제공 하는 동안 데이터 전송 작업에서 형식을 지정 하려면이 함수를 호출 합니다.  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터가 제공 될 수 있으며 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpStgMedium`  
 가리키는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 지정 된 형식의 데이터를 포함 하는 구조입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터가 제공 될 수 있으며 형식을 설명 하는 구조입니다. 지정한 클립보드 형식 이상의 추가 형식 정보를 지정 하려는 경우이 매개 변수에 대 한 값을 제공 `cfFormat`합니다. 이 경우 **NULL**, 다른 필드에 대해 기본값이 사용 됩니다는 **FORMATETC** 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수 즉시 렌더링을 사용 하 여 제공 하기 때문에 데이터를 제공 해야 합니다. 데이터는 필요할 때까지 캐시 됩니다.  
  
 사용 하 여 데이터를 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 구조입니다. 사용할 수도 있습니다는 `CacheGlobalData` 멤버 함수는 데이터 양을 제공 하는 경우 사용 하 여 효율적으로 전송할 수 있을 만큼 적습니다는 `HGLOBAL`합니다.  
  
 호출한 후 `CacheData` 는 **데** 소속 `lpFormatEtc` 의 내용과 `lpStgMedium` 호출자가 아니라 데이터 개체에 의해 소유 됩니다.  
  
 지연 된 렌더링을 사용 하려면 호출는 [DelayRenderData](#delayrenderdata) 또는 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수입니다. 자세한 내용은 지연 된 렌더링에 MFC에서 처리 된 것으로 문서를 참조 [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.  
  
 자세한 내용은 참조는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK에는 구조입니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows sdk에서입니다.  
  
##  <a name="cacheglobaldata"></a>COleDataSource::CacheGlobalData  
 데이터는 제공 하는 동안 데이터 전송 작업에서 형식을 지정 하려면이 함수를 호출 합니다.  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터가 제공 될 수 있으며 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 *hGlobal*  
 지정 된 형식의 데이터를 포함 하는 전역 메모리 블록에 대 한 핸들입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터가 제공 될 수 있으며 형식을 설명 하는 구조입니다. 지정한 클립보드 형식 이상의 추가 형식 정보를 지정 하려는 경우이 매개 변수에 대 한 값을 제공 `cfFormat`합니다. 이 경우 **NULL**, 다른 필드에 대해 기본값이 사용 됩니다는 **FORMATETC** 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 즉시 렌더링; 함수를 호출할 때 데이터를 제공 해야 하므로 데이터를 제공 합니다. 데이터는 필요할 때까지 캐시 됩니다. 사용 하 여는 `CacheData` 많은 양의 데이터 또는 구조적된 저장소 매체 필요한 경우 제공 하는 경우 멤버 함수입니다.  
  
 지연 된 렌더링을 사용 하려면 호출는 [DelayRenderData](#delayrenderdata) 또는 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수입니다. 자세한 내용은 지연 된 렌더링에 MFC에서 처리 된 것으로 문서를 참조 [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.  
  
 자세한 내용은 참조는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK에는 구조입니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows sdk에서입니다.  
  
##  <a name="coledatasource"></a>COleDataSource::COleDataSource  
 `COleDataSource` 개체를 생성합니다.  
  
```  
COleDataSource();
```  
  
##  <a name="delayrenderdata"></a>COleDataSource::DelayRenderData  
 데이터는 제공 하는 동안 데이터 전송 작업에서 형식을 지정 하려면이 함수를 호출 합니다.  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터가 제공 될 수 있으며 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터가 제공 될 수 있으며 형식을 설명 하는 구조입니다. 지정한 클립보드 형식 이상의 추가 형식 정보를 지정 하려는 경우이 매개 변수에 대 한 값을 제공 `cfFormat`합니다. 이 경우 **NULL**, 다른 필드에 대해 기본값이 사용 됩니다는 **FORMATETC** 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 지연 된 렌더링 데이터 즉시 제공 되지 않은 데이터를 제공 합니다. [OnRenderData](#onrenderdata) 또는 [OnRenderGlobalData](#onrenderglobaldata) 데이터를 요청 하려면 멤버 함수를 호출 합니다.  
  
 통해 데이터를 제공 하지 않을 경우이 함수를 사용 하 여 한 `CFile` 개체입니다. 통해 데이터를 제공 하는 경우는 `CFile` 개체를 호출 하는 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수입니다. 자세한 내용은 지연 된 렌더링에 MFC에서 처리 된 것으로 문서를 참조 [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.  
  
 즉시 렌더링을 사용 하려면 호출는 [CacheData](#cachedata) 또는 [CacheGlobalData](#cacheglobaldata) 멤버 함수입니다.  
  
 자세한 내용은 참조는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK에는 구조입니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows sdk에서입니다.  
  
##  <a name="delayrenderfiledata"></a>COleDataSource::DelayRenderFileData  
 데이터는 제공 하는 동안 데이터 전송 작업에서 형식을 지정 하려면이 함수를 호출 합니다.  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터가 제공 될 수 있으며 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터가 제공 될 수 있으며 형식을 설명 하는 구조입니다. 지정한 클립보드 형식 이상의 추가 형식 정보를 지정 하려는 경우이 매개 변수에 대 한 값을 제공 `cfFormat`합니다. 이 경우 **NULL**, 다른 필드에 대해 기본값이 사용 됩니다는 **FORMATETC** 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 지연 된 렌더링 데이터 즉시 제공 되지 않은 데이터를 제공 합니다. [OnRenderFileData](#onrenderfiledata) 데이터를 요청 하려면 멤버 함수를 호출 합니다.  
  
 사용 하려는 경우이 함수를 사용 하 여 한 `CFile` 는 데이터를 제공 하는 개체입니다. 사용 하지 않을 경우는 `CFile` 개체를 호출 하는 [DelayRenderData](#delayrenderdata) 멤버 함수입니다. 자세한 내용은 지연 된 렌더링에 MFC에서 처리 된 것으로 문서를 참조 [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.  
  
 즉시 렌더링을 사용 하려면 호출는 [CacheData](#cachedata) 또는 [CacheGlobalData](#cacheglobaldata) 멤버 함수입니다.  
  
 자세한 내용은 참조는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK에는 구조입니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows sdk에서입니다.  
  
##  <a name="delaysetdata"></a>COleDataSource::DelaySetData  
 데이터 원본의 내용을 변경 기능을 지원 하려면이 함수를 호출 합니다.  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터를 배치할 수 인 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터를 교체의 형식을 설명 하는 구조입니다. 지정한 클립보드 형식 이상의 추가 형식 정보를 지정 하려는 경우이 매개 변수에 대 한 값을 제공 `cfFormat`합니다. 이 경우 **NULL**, 다른 필드에 대해 기본값이 사용 됩니다는 **FORMATETC** 구조입니다.  
  
### <a name="remarks"></a>설명  
 [OnSetData](#onsetdata) 이 프레임 워크에서 호출 됩니다. 프레임 워크에서 데이터 원본을 반환 될 때만 사용 됩니다 [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource)합니다. 경우 `DelaySetData` 를 호출 하지 않으면 프로그램 `OnSetData` 함수 호출 되지 것입니다. `DelaySetData`각 클립보드를 호출 해야 합니다 또는 **FORMATETC** 지 원하는 형식.  
  
 자세한 내용은 참조는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK에는 구조입니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows sdk에서입니다.  
  
##  <a name="dodragdrop"></a>Coledatasource:: Dodragdrop  
 호출 된 `DoDragDrop` 멤버 함수에서 일반적으로이 데이터 원본에 대 한 끌어서 놓기 작업을 수행 하는 [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) 처리기입니다.  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwEffects`  
 끌어서 놓기 작업 허용 되는이 데이터 원본에서입니다. 다음 중 하나 이상을 하나일 수 있습니다.  
  
- `DROPEFFECT_COPY`복사 작업을 수행할 수 있습니다.  
  
- `DROPEFFECT_MOVE`이동 작업을 수행할 수 있습니다.  
  
- `DROPEFFECT_LINK`원래 데이터를 전송 된 데이터에서 링크를 설정할 수 없습니다.  
  
- `DROPEFFECT_SCROLL`끌기 스크롤 작업이 발생할 수를 나타냅니다.  
  
 `lpRectStartDrag`  
 끌기 실제로 시작 위치를 정의 하는 사각형에 대 한 포인터입니다. 자세한 내용은 아래 설명 부분을 참조하십시오.  
  
 *pDropSource*  
 놓기 소스를 가리킵니다. 경우 **NULL** 의 기본 구현을 다음 [COleDropSource](../../mfc/reference/coledropsource-class.md) 사용 됩니다.  
  
### <a name="return-value"></a>반환 값  
 끌어서 놓기 작업;에 의해 생성 된 효과 그렇지 않으면 `DROPEFFECT_NONE` 제공 된 사각형을 벗어나기 전에 마우스 단추를 놓은 때문에 에서만 작업을 시작 하는 경우.  
  
### <a name="remarks"></a>설명  
 끌어서 놓기 작업이 즉시 시작 되지 않습니다. 마우스 커서가으로 지정 된 사각형을 벗어날 때까지 기다렸다가 `lpRectStartDrag` 지정 된 기간 (밀리초) 조건이 충족 될 때까지 또는 합니다. 경우 `lpRectStartDrag` 은 **NULL**, 사각형의 크기는 1 픽셀입니다.  
  
 레지스트리 키 설정 지연 시간 지정 됩니다. 호출 하 여 지연 시간을 변경할 수 있습니다 [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) 또는 [cwinapp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)합니다. 지연 시간을 지정 하지 않으면 기본값은 200 밀리초 사용 됩니다. 끌어서 지연 시간을 다음과 같이 저장 됩니다.  
  
-   Windows NT 끌어서 지연 시간 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay에 저장 됩니다.  
  
-   Windows 3.x 끌어서 지연 시간 WIN에 저장 됩니다. INI 파일 [Windows} 섹션.  
  
-   Windows 95/98 끌어서 지연 시간 WIN의 캐시 된 버전에 저장 됩니다. INI 합니다.  
  
 연기 된 정보는 레지스트리에 저장 됩니다는 방법에 대 한 자세한 내용은 끌어에 대 한 또는 합니다. INI 파일 참조 [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) Windows sdk에서입니다.  
  
 자세한 내용은 문서 참조 [끌어서 놓기: 놓기 소스 구현](../../mfc/drag-and-drop-implementing-a-drop-source.md)합니다.  
  
##  <a name="empty"></a>COleDataSource::Empty  
 비어 있는 것으로이 함수 호출의 `COleDataSource` 데이터의 개체입니다.  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>설명  
 다시 사용할 수 있도록 지연 렌더링 형식의 비우기와 캐시 모두.  
  
 자세한 내용은 참조 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Windows sdk에서입니다.  
  
##  <a name="flushclipboard"></a>COleDataSource::FlushClipboard  
 클립보드에 사용 중이 고 다음 응용 프로그램을 종료 한 후 클립보드의에서 데이터를 붙여넣을 수 있는 데이터를 렌더링 합니다.  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>설명  
 사용 하 여 [SetClipboard](#setclipboard) 클립보드에 데이터를 저장 합니다.  
  
##  <a name="getclipboardowner"></a>COleDataSource::GetClipboardOwner  
 클립보드의 데이터 이후 변경 되었는지 여부를 결정 [SetClipboard](#setclipboard) 가 마지막으로 호출 하 고이 경우 현재 소유자를 식별 합니다.  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>반환 값  
 현재 클립보드에 데이터 원본 또는 **NULL** 클립보드에 없으면 또는 호출 응용 프로그램이 클립보드를 소유 하지 않은 경우.  
  
##  <a name="onrenderdata"></a>COleDataSource::OnRenderData  
 지정 된 형식의 데이터를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 정보가 요청 된 형식을 지정 하는 구조입니다.  
  
 `lpStgMedium`  
 가리키는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 반환 될 데이터는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정 된 형식에 이전에 배치 이란는 `COleDataSource` 를 사용 하 여 개체는 [DelayRenderData](#delayrenderdata) 또는 [DelayRenderFileData](#delayrenderfiledata) 지연 된 렌더링 하기 위한 멤버 함수입니다. 이 함수의 기본 구현을 호출 합니다 [OnRenderFileData](#onrenderfiledata) 또는 [OnRenderGlobalData](#onrenderglobaldata) 각각 제공 된 저장소 미디어는 파일 또는 메모리를 하는 경우. 이러한 형식은 모두를 제공 하는 그런 다음 기본 구현은 0을 반환 하 고 아무 작업도 수행 하지 않습니다. 자세한 내용은 지연 된 렌더링에 MFC에서 처리 된 것으로 문서를 참조 [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.  
  
 경우 `lpStgMedium` ->  *tymed* 은 **TYMED_NULL**, **STGMEDIUM** 할당 되 고에 지정 된 대로 입력 해야 *lpFormatEtc-> tymed*합니다. 없으면 **TYMED_NULL**, **STGMEDIUM** 데이터와 함께에서 채워야 합니다.  
  
 고급 재정의할 수 있습니다. 요청 된 형식 및 중간 규모의 데이터를 제공 하려면이 함수를 재정의 합니다. 데이터에 따라 대신이 함수의 다른 버전 중 하나를 재정의 하는 것이 좋습니다. 데이터가 작고 크기가 고정 되어 있으면 재정의 `OnRenderGlobalData`합니다. 데이터 파일에는 가변 크기의 경우 재정의 `OnRenderFileData`합니다.  
  
 자세한 내용은 참조는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조는 [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) 열거형 형식 및 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK에서  
  
##  <a name="onrenderfiledata"></a>COleDataSource::OnRenderFileData  
 지정 된 저장소 미디어로 파일을 때 지정 된 형식의 데이터를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 정보가 요청 된 형식을 지정 하는 구조입니다.  
  
 `pFile`  
 가리키는 [CFile](../../mfc/reference/cfile-class.md) 데이터 렌더링 해야 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정 된 형식에 이전에 배치 이란는 `COleDataSource` 를 사용 하 여 개체는 [DelayRenderData](#delayrenderdata) 지연 된 렌더링 하기 위한 멤버 함수입니다. 이 함수의 기본 구현은 단순히 반환 **FALSE**합니다.  
  
 고급 재정의할 수 있습니다. 요청 된 형식 및 중간 규모의 데이터를 제공 하려면이 함수를 재정의 합니다. 데이터에 따라 대신이 함수는 다른 버전 중 하나를 재정의 하는 것이 좋습니다. 여러 저장소 미디어 처리 하려는 경우 재정의 [OnRenderData](#onrenderdata)합니다. 데이터 파일에는 가변 크기의 경우 재정의 `OnRenderFileData`합니다. 자세한 내용은 지연 된 렌더링에 MFC에서 처리 된 것으로 문서를 참조 [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.  
  
 자세한 내용은 참조는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조 및 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows sdk에서입니다.  
  
##  <a name="onrenderglobaldata"></a>COleDataSource::OnRenderGlobalData  
 지정 된 저장소 미디어로 전역 메모리 때 지정 된 형식의 데이터를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 정보가 요청 된 형식을 지정 하는 구조입니다.  
  
 `phGlobal`  
 반환 될 데이터는 전역 메모리에 대 한 핸들을 가리킵니다. 이 매개 변수 수 하나에 아직 할당 되지 경우 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정 된 형식에 이전에 배치 이란는 `COleDataSource` 를 사용 하 여 개체는 [DelayRenderData](#delayrenderdata) 지연 된 렌더링 하기 위한 멤버 함수입니다. 이 함수의 기본 구현은 단순히 반환 **FALSE**합니다.  
  
 경우 `phGlobal` 은 **NULL**, 다음 새 `HGLOBAL` 할당 되 고 반환 해야 `phGlobal`합니다. 그렇지 않은 경우는 `HGLOBAL` 에 지정 된 `phGlobal` 데이터로 채워야 합니다. 데이터의 양을에 배치 된 `HGLOBAL` 메모리 블록의 현재 크기를 넘지 않아야 합니다. 또한, 더 큰 크기로 블록 다시 할당할 수 없습니다.  
  
 고급 재정의할 수 있습니다. 요청 된 형식 및 중간 규모의 데이터를 제공 하려면이 함수를 재정의 합니다. 데이터에 따라 대신이 함수의 다른 버전 중 하나를 재정의 하는 것이 좋습니다. 여러 저장소 미디어 처리 하려는 경우 재정의 [OnRenderData](#onrenderdata)합니다. 데이터 파일에는 가변 크기의 경우 재정의 [OnRenderFileData](#onrenderfiledata)합니다. 자세한 내용은 지연 된 렌더링에 MFC에서 처리 된 것으로 문서를 참조 [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.  
  
 자세한 내용은 참조는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조 및 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows sdk에서입니다.  
  
##  <a name="onsetdata"></a>COleDataSource::OnSetData  
 설정 하거나 데이터를 바꿀지를 프레임 워크에서 호출 된 `COleDataSource` 지정 된 형식의 개체입니다.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터를 대체 형식을 지정 하는 구조입니다.  
  
 `lpStgMedium`  
 가리키는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 의 현재 내용을 대체 하는 데이터를 포함 하는 구조는 `COleDataSource` 개체입니다.  
  
 `bRelease`  
 함수 호출을 완료 한 후 저장 미디어의 소유권을 가진 사용자를 나타냅니다. 호출자에 게 저장 매체를 대신 하 여 할당 된 리소스를 해제 하는 데 담당자 결정 합니다. 호출자에 게가 작업을 설정 하 여 수행 `bRelease`합니다. 경우 `bRelease` 가 0이 아닌 경우 데이터 원본 사용을 마칠 때 미디어 해제 소유권을 갖습니다. 때 `bRelease` 는 0이 고, 호출자에 게 소유권을 갖고 데이터 원본은 호출의 지속 기간 동안만 저장 매체를 사용할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 데이터 원본 변경 내용이 데이터를 소유는 성공적으로 가져온 것입니다. 즉, 고려 되지 소유권 경우 `OnSetData` 0을 반환 합니다. 데이터 원본 변수를 사용할 경우 소유권에 저장소 매체를 호출 하 여 해제 된 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) 함수입니다.  
  
 기본 구현은 아무 작업도 수행하지 않습니다. 지정 된 형식의 데이터를 교체 하려면이 함수를 재정의 합니다. 고급 재정의할 수 있습니다.  
  
 자세한 내용은 참조는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조 및 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) 및 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK에서 작동 합니다.  
  
##  <a name="setclipboard"></a>COleDataSource::SetClipboard  
 에 포함 된 데이터는 `COleDataSource` 개체는 다음 기능 중 하나를 호출한 후 클립보드에 복사: [CacheData](#cachedata), [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata), 또는 [DelayRenderFileData](#delayrenderfiledata)합니다.  
  
```  
void SetClipboard();
```  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDataObject 클래스](../../mfc/reference/coledataobject-class.md)
