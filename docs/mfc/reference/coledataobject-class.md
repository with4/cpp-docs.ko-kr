---
title: COleDataObject 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
dev_langs:
- C++
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9cd159597440dfb55bbe8abe147623096cdf449
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374512"
---
# <a name="coledataobject-class"></a>COleDataObject 클래스
끌어 놓기를 통해 클립보드에서 또는 포함된 OLE 항목에서 다양한 형식의 데이터를 검색하기 위해 데이터를 전송하는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleDataObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDataObject::COleDataObject](#coledataobject)|`COleDataObject` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDataObject::Attach](#attach)|지정 된 OLE 데이터 개체에 연결 된 `COleDataObject`합니다.|  
|[COleDataObject::AttachClipboard](#attachclipboard)|클립보드에 데이터 개체를 연결 합니다.|  
|[COleDataObject::BeginEnumFormats](#beginenumformats)|하나에 대 한 볼륨이 나 보다 후속 준비 `GetNextFormat` 호출 합니다.|  
|[COleDataObject::Detach](#detach)|연결 된 분리 `IDataObject` 개체입니다.|  
|[COleDataObject::GetData](#getdata)|지정 된 형식에서 연결 된 OLE 데이터 개체에서 데이터를 복사 합니다.|  
|[COleDataObject::GetFileData](#getfiledata)|에 연결 된 OLE 데이터 개체에서 데이터를 복사는 `CFile` 지정 된 형식의 포인터입니다.|  
|[COleDataObject::GetGlobalData](#getglobaldata)|에 연결 된 OLE 데이터 개체에서 데이터를 복사는 `HGLOBAL` 지정 된 형식에서입니다.|  
|[COleDataObject::GetNextFormat](#getnextformat)|사용 가능한 다음 데이터 형식을 반환합니다.|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|데이터를 지정된 된 형식으로 사용할 수 있는지 여부를 확인 합니다.|  
|[COleDataObject::Release](#release)|분리 및 연결 된 해제 `IDataObject` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `COleDataObject` 기본 클래스는 없습니다.  
  
 이러한 종류의 데이터 전송 원본과 대상이 포함 합니다. 데이터 원본 개체로 구현 되는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 클래스입니다. 대상 응용 프로그램에 데이터를 삭제 또는 개체 클립보드에서 붙여넣기 작업을 수행 하도록 요청 될 때마다는 `COleDataObject` 클래스를 만들어야 합니다.  
  
 이 클래스를 사용 하면 데이터가 지정된 된 형식에 있는지 여부를 확인할 수 있습니다. 또한 사용 가능한 데이터 형식을 열거 하 또는 지정 된 형식을 사용할 수 있는지 확인 고 기본 설정된 된 형식에 데이터를 검색 합니다. 사용을 포함 하는 여러 가지 방법으로, 개체 검색을 수행할 수 있습니다는 [CFile](../../mfc/reference/cfile-class.md), `HGLOBAL`, 또는 **STGMEDIUM** 구조입니다.  
  
 자세한 내용은 참조는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK에는 구조입니다.  
  
 응용 프로그램에서 데이터 개체를 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `COleDataObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="attach"></a>  COleDataObject::Attach  
 연결 하려면이 함수 호출의 `COleDataObject` OLE 데이터 개체는 개체입니다.  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpDataObject*  
 OLE 데이터 개체를 가리킵니다.  
  
 `bAutoRelease`  
 **TRUE** OLE 데이터 개체 해야 하면 출시 시기는 `COleDataObject` 개체 소멸 되지 않았으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Windows sdk에서입니다.  
  
##  <a name="attachclipboard"></a>  COleDataObject::AttachClipboard  
 현재 클립보드에 있는 데이터 개체를 연결 하려면이 함수 호출의 `COleDataObject` 개체입니다.  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 데이터 개체를 해제 될 때까지 클립보드를 잠급니다이 함수를 호출 합니다. 데이터 개체에 대 한 소멸자에서 해제 되 고 `COleDataObject`합니다. 자세한 내용은 참조 [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048) 및 [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Win32 설명서의 합니다.  
  
##  <a name="beginenumformats"></a>  COleDataObject::BeginEnumFormats  
 이 함수에 대 한 후속 호출에 대 한 준비를 호출 `GetNextFormat` 항목에서 데이터 형식의 목록을 검색 합니다.  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>설명  
 호출한 후 `BeginEnumFormats`,이 데이터 개체에서 지원 되는 첫 번째 형식 위치에 저장 됩니다. 에 대 한 연속 호출은 `GetNextFormat` 데이터 개체에 사용 가능한 형식 목록을 열거 합니다.  
  
 지정 된 형식으로 데이터의 가용성을 확인 하려면 사용 하 여 [COleDataObject::IsDataAvailable](#isdataavailable)합니다.  
  
 자세한 내용은 참조 [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) Windows sdk에서입니다.  
  
##  <a name="coledataobject"></a>  COleDataObject::COleDataObject  
 `COleDataObject` 개체를 생성합니다.  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>설명  
 에 대 한 호출 [COleDataObject::Attach](#attach) 또는 [COleDataObject::AttachClipboard](#attachclipboard) 다른를 호출 하기 전에 수행 해야 `COleDataObject` 함수입니다.  
  
> [!NOTE]
>  에 대 한 포인터를 끌어서 놓기 처리기 매개 변수 중 하나 이므로 `COleDataObject`, 끌어서 놓기 지원 하기 위해이 생성자를 호출할 필요가 없습니다.  
  
##  <a name="detach"></a>  COleDataObject::Detach  
 이 함수를 분리를 호출 하는 `COleDataObject` 데이터 개체를 해제 하지 않고 연결된 된 OLE 데이터 개체에서 개체입니다.  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>반환 값  
 분리 된 OLE 데이터 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getdata"></a>  COleDataObject::GetData  
 지정 된 형식의 항목에서 데이터를 검색 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터를 반환할 인 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpStgMedium`  
 가리키는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 데이터를 받을 구조입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터 반환 형식을 설명 하는 구조입니다. 지정한 클립보드 형식 이상의 추가 형식 정보를 지정 하려는 경우이 매개 변수에 대 한 값을 제공 `cfFormat`합니다. 경우 **NULL**, 기본 값이 다른 필드에서 사용 되는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows sdk에서입니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows sdk에서입니다.  
  
##  <a name="getfiledata"></a>  COleDataObject::GetFileData  
 이 함수를 만드는 호출는 `CFile` 또는 `CFile`-파생 개체에 지정 된 형식의 데이터를 검색 하 고는 `CFile` 포인터입니다.  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터를 반환할 인 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터 반환 형식을 설명 하는 구조입니다. 지정한 클립보드 형식 이상의 추가 형식 정보를 지정 하려는 경우이 매개 변수에 대 한 값을 제공 `cfFormat`합니다. 경우 **NULL**, 기본 값이 다른 필드에서 사용 되는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 새 포인터 `CFile` 또는 `CFile`-파생 된 개체 데이터를 포함 하 고, 그렇지 않으면 성공 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 데이터에 저장 된 미디어를 따라 반환 값에서 가리키는 실제 형식이 될 수 있습니다 `CFile`, `CSharedFile`, 또는 `COleStreamFile`합니다.  
  
> [!NOTE]
>  `CFile` 호출자가이 함수의 반환 값으로 액세스 하는 개체를 소유 합니다. 것은 호출자의 책임 **삭제** 는 `CFile` 있으므로 파일을 닫는 개체입니다.  
  
 자세한 내용은 참조 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows sdk에서입니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows sdk에서입니다.  
  
##  <a name="getglobaldata"></a>  COleDataObject::GetGlobalData  
 전역 메모리 블록을 할당 하 고에 지정 된 형식의 데이터를 검색 하려면이 함수를 호출는 `HGLOBAL`합니다.  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터를 반환할 인 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터 반환 형식을 설명 하는 구조입니다. 지정한 클립보드 형식 이상의 추가 형식 정보를 지정 하려는 경우이 매개 변수에 대 한 값을 제공 `cfFormat`합니다. 경우 **NULL**, 기본 값이 다른 필드에서 사용 되는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 데이터를 포함 하는 전역 메모리 블록의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows sdk에서입니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows sdk에서입니다.  
  
##  <a name="getnextformat"></a>  COleDataObject::GetNextFormat  
 항목에서 데이터를 검색 하기 위해 사용할 수 있는 모든 형식에이 반복적으로 호출 합니다.  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조체 함수 호출에서 반환 된 형식 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 다른 경우 0이 아닌 형식은 사용할 수 있습니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 호출한 후 [COleDataObject::BeginEnumFormats](#beginenumformats),이 데이터 개체에서 지원 되는 첫 번째 형식 위치에 저장 됩니다. 에 대 한 연속 호출은 `GetNextFormat` 데이터 개체에 사용 가능한 형식 목록을 열거 합니다. 이러한 함수를 사용 하 여는 사용 가능한 형식을 나열 합니다.  
  
 지정 된 형식의 가용성을 확인 하려면 호출 [COleDataObject::IsDataAvailable](#isdataavailable)합니다.  
  
 자세한 내용은 참조 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) Windows sdk에서입니다.  
  
##  <a name="isdataavailable"></a>  COleDataObject::IsDataAvailable  
 OLE 항목에서 데이터를 검색 하기 위해 사용할 수 있는 특정 형식 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 구조에 사용 되는 클립보드 데이터 형식에서 가리키는 `lpFormatEtc`합니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 원하는 형식을 설명 하는 구조입니다. 지정한 클립보드 형식 이상의 추가 형식 정보를 지정 하려는 경우에이 매개 변수의 값을 제공 `cfFormat`합니다. 경우 **NULL**, 기본 값이 다른 필드에서 사용 되는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 데이터는 지정된 된 형식에서 사용할 수 있는 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 호출 하기 전에 유용 `GetData`, `GetFileData`, 또는 `GetGlobalData`합니다.  
  
 자세한 내용은 참조 [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows sdk에서입니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata)합니다.  
  
##  <a name="release"></a>  COleDataObject::Release  
 소유권을 해제 하려면이 함수 호출의 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) 이전에 연결 된 개체는 `COleDataObject` 개체입니다.  
  
```  
void Release();
```  
  
### <a name="remarks"></a>설명  
 `IDataObject` 연결 된는 `COleDataObject` 호출 하 여 **연결** 또는 `AttachClipboard` 명시적으로 또는 프레임 워크에서. 경우는 `bAutoRelease` 의 매개 변수 **연결** 은 **FALSE**, `IDataObject` 개체 해제 되지 것입니다. 이 경우 호출자는 해제를 위한 처리는 `IDataObject` 호출 하 여 [iunknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDataSource 클래스](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem 클래스](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)
