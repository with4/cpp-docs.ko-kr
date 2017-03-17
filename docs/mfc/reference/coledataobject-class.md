---
title: "COleDataObject 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- drag and drop [C++], MFC support
- Clipboard [C++], OLE support
- uniform data transfer
- OLE [C++], uniform data transfer
- Clipboard [C++], MFC support
- OLE Clipboard [C++], support
- IDataObject interface, MFC encapsulation
- data transfer [C++]
- data transfer [C++], OLE
- OLE data transfer [C++]
- COleDataObject class
- uniform data transfer, OLE
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f30ca208252fe81f1e47d9e8f817cb9137656540
ms.lasthandoff: 02/24/2017

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
|[COleDataObject::AttachClipboard](#attachclipboard)|클립보드에 저장 되는 데이터 개체에 연결 합니다.|  
|[COleDataObject::BeginEnumFormats](#beginenumformats)|하나에 대 한 볼륨이 나 더 후속 준비 `GetNextFormat` 호출 합니다.|  
|[COleDataObject::Detach](#detach)|연결 된 분리 `IDataObject` 개체입니다.|  
|[COleDataObject::GetData](#getdata)|지정된 된 형식에 연결 된 OLE 데이터 개체에서 데이터를 복사 합니다.|  
|[COleDataObject::GetFileData](#getfiledata)|에 연결된 된 OLE 데이터 개체에서 데이터를 복사는 `CFile` 지정 된 형식의 포인터입니다.|  
|[COleDataObject::GetGlobalData](#getglobaldata)|에 연결된 된 OLE 데이터 개체에서 데이터를 복사는 `HGLOBAL` 지정 된 형식에서입니다.|  
|[COleDataObject::GetNextFormat](#getnextformat)|사용 가능한 다음 데이터 형식을 반환합니다.|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|데이터를 지정된 된 형식에서 사용할 수 있는지 여부를 확인 합니다.|  
|[COleDataObject::Release](#release)|분리 및 연결 된 해제 `IDataObject` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 `COleDataObject`기본 클래스는 없습니다.  
  
 이러한 종류의 데이터 전송 원본과 대상에 포함 합니다. 데이터 소스 개체로 구현 되는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 클래스입니다. 때마다 대상 응용 프로그램 데이터를 삭제 했거나 개체 클립보드에서 붙여넣기 작업을 수행 하 라는 메시지가 표시 되는 `COleDataObject` 클래스를 만들어야 합니다.  
  
 이 클래스를 사용 하면 데이터가 지정된 된 형식에 있는지 여부를 확인할 수 있습니다. 또한 사용 가능한 데이터 형식 열거 또는 지정 된 형식을 사용할 수 있는지 확인을 기본 설정된 된 형식에서 데이터를 검색 합니다. 사용을 포함 하는 여러 가지 방법으로, 개체 검색을 수행할 수 있습니다는 [CFile](../../mfc/reference/cfile-class.md), `HGLOBAL`, 또는 **STGMEDIUM** 구조입니다.  
  
 자세한 내용은 참조는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 응용 프로그램에서 데이터 개체를 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `COleDataObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="attach"></a>COleDataObject::Attach  
 연결 하려면이 함수를 호출 하는 `COleDataObject` 개체는 OLE 데이터 개체를 사용 합니다.  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpDataObject*  
 OLE 데이터 개체를 가리킵니다.  
  
 `bAutoRelease`  
 **True 이면** OLE 데이터 개체 해야 하면 면이 해제는 `COleDataObject` 개체가 소멸 되 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="attachclipboard"></a>COleDataObject::AttachClipboard  
 클립보드에 현재 있는 데이터 개체를 연결 하려면이 함수를 호출 하 여 `COleDataObject` 개체입니다.  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  이 데이터 개체가 해제 될 때까지 클립보드를 잠급니다이 함수를 호출 합니다. 데이터 개체에 대 한 소멸자에서 해제 되 고 `COleDataObject`합니다. 자세한 내용은 참조 [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048) 및 [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Win32 설명서의 합니다.  
  
##  <a name="beginenumformats"></a>COleDataObject::BeginEnumFormats  
 이 함수에 대 한 후속 호출에 대 한 준비를 호출 `GetNextFormat` 항목에서 데이터 형식의 목록을 검색 합니다.  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>주의  
 호출한 후 `BeginEnumFormats`,이 데이터 개체에서 지원 되는 첫 번째 형식의 위치에 저장 됩니다. 연속적으로 호출 `GetNextFormat` 데이터 개체에 사용할 수 있는 형식의 목록을 열거 합니다.  
  
 사용 하 여 지정된 된 형식으로 데이터의 가용성을 확인 하려면 [COleDataObject::IsDataAvailable](#isdataavailable)합니다.  
  
 자세한 내용은 참조 [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="coledataobject"></a>COleDataObject::COleDataObject  
 `COleDataObject` 개체를 생성합니다.  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>주의  
 에 대 한 호출 [COleDataObject::Attach](#attach) 또는 [COleDataObject::AttachClipboard](#attachclipboard) 다른를 호출 하기 전에 만들어야 `COleDataObject` 함수입니다.  
  
> [!NOTE]
>  에 대 한 포인터를 끌어서 놓기 처리기 매개 변수 중 하나 이므로 `COleDataObject`, 끌어서 놓기 지원 하기 위해이 생성자를 호출할 필요가 없습니다.  
  
##  <a name="detach"></a>COleDataObject::Detach  
 이 함수를 분리를 호출 하는 `COleDataObject` 데이터 개체를 해제 하지 않고 연결된 된 OLE 데이터 개체에서 개체입니다.  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>반환 값  
 분리 된 OLE 데이터 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getdata"></a>COleDataObject::GetData  
 지정 된 형식의 항목에서 데이터를 검색 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터 반환 되는 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpStgMedium`  
 가리키는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 데이터를 받을 구조입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터 반환 형식을 설명 하는 구조입니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우이 매개 변수 값을 제공 `cfFormat`합니다. 있으면 **NULL**, 다른 필드에 대 한 기본 값이 사용 되는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getfiledata"></a>COleDataObject::GetFileData  
 만들려면이 함수를 호출 하는 `CFile` 또는 `CFile`-파생 개체에 지정 된 형식의 데이터를 검색 하 고는 `CFile` 포인터입니다.  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터 반환 되는 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터 반환 형식을 설명 하는 구조입니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우이 매개 변수 값을 제공 `cfFormat`합니다. 있으면 **NULL**, 다른 필드에 대 한 기본 값이 사용 되는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 새 포인터 `CFile` 또는 `CFile`-성공적이 고 그렇지 않으면 데이터를 포함 하는 파생 된 개체 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 데이터에 저장 된 미디어를 따라 반환 값은가 가리키는 실제 형식이 될 수 있습니다 `CFile`, `CSharedFile`, 또는 `COleStreamFile`합니다.  
  
> [!NOTE]
>  `CFile` 이 함수의 반환 값으로 액세스 하는 개체를 호출자가 소유 합니다. 것은 호출자의 책임 **삭제** 는 `CFile` 있으므로 파일을 닫는 개체입니다.  
  
 자세한 내용은 참조 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getglobaldata"></a>COleDataObject::GetGlobalData  
 전역 메모리 블록을 할당 하 고에 지정 된 형식의 데이터를 검색 하려면이 함수를 호출 하는 `HGLOBAL`합니다.  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 데이터 반환 되는 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터 반환 형식을 설명 하는 구조입니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우이 매개 변수 값을 제공 `cfFormat`합니다. 있으면 **NULL**, 다른 필드에 대 한 기본 값이 사용 되는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 데이터를 포함 하는 전역 메모리 블록의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getnextformat"></a>COleDataObject::GetNextFormat  
 반복 해 서 항목에서 데이터 검색에 사용할 수 있는 모든 형식을 가져오려면이 함수를 호출 합니다.  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 함수 호출에서 반환 된 형식 정보를 수신 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 다른 경우에 0이 아닌 형식은 사용할 수 있습니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 호출한 후 [COleDataObject::BeginEnumFormats](#beginenumformats),이 데이터 개체에서 지원 되는 첫 번째 형식의 위치에 저장 됩니다. 연속적으로 호출 `GetNextFormat` 데이터 개체에 사용할 수 있는 형식의 목록을 열거 합니다. 이러한 함수를 사용 하 여 사용 가능한 형식 목록입니다.  
  
 지정 된 형식의 가용성을 확인 하려면 호출 [COleDataObject::IsDataAvailable](#isdataavailable)합니다.  
  
 자세한 내용은 참조 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="isdataavailable"></a>COleDataObject::IsDataAvailable  
 OLE 항목에서 데이터 검색에 사용할 수 있는 특정 형식 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cfFormat`  
 구조에 사용할 클립보드 데이터 형식에서 가리키는 `lpFormatEtc`합니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환 된 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수입니다.  
  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 원하는 형식을 설명 하는 구조입니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 있으면 **NULL**, 다른 필드에 대 한 기본 값이 사용 되는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 데이터가 지정된 된 형식에서 사용할 수 있는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 호출 하기 전에 유용 `GetData`, `GetFileData`, 또는 `GetGlobalData`합니다.  
  
 자세한 내용은 참조 [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 자세한 내용은 참조 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata)합니다.  
  
##  <a name="release"></a>COleDataObject::Release  
 소유권을 해제 하려면이 함수를 호출 하는 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) 이전에 연결 된 개체는 `COleDataObject` 개체입니다.  
  
```  
void Release();
```  
  
### <a name="remarks"></a>주의  
 `IDataObject` 와 연결 된는 `COleDataObject` 를 호출 하 여 **연결** 또는 `AttachClipboard` 프레임 워크에 의해 명시적으로 또는 합니다. 하는 경우는 `bAutoRelease` 의 매개 변수 **연결** 는 **FALSE**, `IDataObject` 개체 해제 되지 것입니다. 이 경우 호출자는 해제 하는 데는 `IDataObject` 를 호출 하 여 [iunknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDataSource 클래스](../../mfc/reference/coledatasource-class.md)   
 [활성화 클래스](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)

