---
title: "OLE 컨트롤의 지 속성 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE controls, persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b8bbf72a1ea16b37dabf88c5d41a34b1a03ba0d1
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="persistence-of-ole-controls"></a>OLE 컨트롤의 지속성
OLE 컨트롤의 한 기능을 속성 지 속성 (또는 serialization)는 OLE 컨트롤을 읽거나 파일 또는 스트림에서 속성 값을 쓸 수 있습니다. 컨테이너 응용 프로그램 serialization을 사용 응용 프로그램 컨트롤 소멸 된 후에 컨트롤의 속성 값을 저장할 수 있습니다. OLE 컨트롤의 속성 값은 파일에서 읽을 수 있습니다 또는 나중에 스트림 컨트롤의 새 인스턴스가 만들어집니다.  
  
### <a name="persistence-of-ole-controls"></a>OLE 컨트롤의 지속성  
  
|||  
|-|-|  
|[PX_Blob](#px_blob)|이진 대형 개체 (BLOB) 데이터를 저장 하는 컨트롤 속성을 교환 합니다.|  
|[PX_Bool](#px_bool)|교환 컨트롤 속성 형식의 **BOOL**합니다.|  
|[PX_Color](#px_color)|컨트롤의 색 속성을 교환합니다.|  
|[PX_Currency](#px_currency)|교환 컨트롤 속성 형식의 **CY**합니다.|  
|[PX_DataPath](#px_datapath)|컨트롤 형식의 속성을 교환 `CDataPathProperty`합니다.|  
|[PX_Double](#px_double)|교환 컨트롤 속성 형식의 **이중**합니다.|  
|[PX_Font](#px_font)|컨트롤의 글꼴 속성을 교환합니다.|  
|[PX_Float](#px_float)|교환 컨트롤 속성 형식의 **float**합니다.|  
|[PX_IUnknown](#px_iunknown)|정의 되지 않은 형식의 컨트롤 속성을 교환합니다.|  
|[PX_Long](#px_long)|교환 컨트롤 속성 형식의 **긴**합니다.|  
|[PX_Picture](#px_picture)|컨트롤의 사진 속성을 교환합니다.|  
|[PX_Short](#px_short)|교환 컨트롤 속성 형식의 **짧은**합니다.|  
|[PX_ULong](#px_ulong)|교환 컨트롤 속성 형식의 **ULONG**합니다.|  
|[PX_UShort](#px_ushort)|교환 컨트롤 속성 형식의 **USHORT**합니다.|  
|[PXstring](#px_string)|문자 문자열 컨트롤 속성을 교환합니다.|  
|[PX_VBXFontConvert](#px_vbxfontconvert)|에 OLE 컨트롤의 글꼴 속성 VBX 컨트롤의 글꼴 관련 속성을 교환합니다.|  
  
 또한는 `AfxOleTypeMatchGuid` 간의 일치 여부를 테스트 하려면 전역 함수는 제공 되는 `TYPEDESC` 및 지정 된 GUID입니다.  
  
##  <a name="px_blob"></a>PX_Blob  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 직렬화 또는 binary large object (BLOB) 데이터를 저장 하는 속성을 초기화 합니다.  
  
```  
 
BOOL  
PX_Blob(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    HGLOBAL& 
hBlob  ,  
    HGLOBAL 
hBlobDefault  
= NULL);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `hBlob`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `hBlobDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은에서 읽거나 쓸에서 참조를 변수에 `hBlob`를 적절 하 게 합니다. 이 변수를 초기화 해야 **NULL** 처음 호출 하기 전에 `PX_Blob` 처음으로 (일반적으로 이렇게 컨트롤의 생성자에서). 경우 `hBlobDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 초기화 또는 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
 핸들 `hBlob` 및 `hBlobDefault` 다음을 포함 하는 메모리 블록을를 참조 하십시오.  
  
-   A `DWORD` 다음에 나오는 이진 데이터의 길이 (바이트)를 포함 하 여 바로 뒤에  
  
-   실제 이진 데이터를 포함 하는 메모리의 블록입니다.  
  
 `PX_Blob` Windows를 사용 하 여 메모리를 할당 합니다 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) API를 BLOB 형식 속성을 로드 하는 경우. 이 메모리를 비우는 책임이 있습니다. 따라서 컨트롤의 소멸자를 호출 해야 [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) BLOB 형식 속성에 대해 해제에 대 한 핸들을 컨트롤에 할당 된 메모리입니다.  
  
##  <a name="px_bool"></a>PX_Bool  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 형식의 속성을 초기화 하는 함수 **BOOL**합니다.  
  
```  
 
BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& bValue);

BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& 
bValue  ,  
    BOOL bDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `bValue`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `bDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은에서 읽거나 쓸에서 참조를 변수에 `bValue`를 적절 하 게 합니다. 경우 `bDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_color"></a>PX_Color  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 형식의 속성을 초기화 하는 함수 **OLE_COLOR**합니다.  
  
```  
 
BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& 
clrValue  ,  
    OLE_COLOR 
clrDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `clrValue`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `clrDefault`  
 컨트롤 개발자가 정의 된 속성에 대 한 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은에서 읽거나 쓸에서 참조를 변수에 `clrValue`를 적절 하 게 합니다. 경우 `clrDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_currency"></a>PX_Currency  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 형식의 속성을 초기화 하는 함수 **통화**합니다.  
  
```  
 
BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& cyValue);

BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& 
cyValue  ,  
    CY cyDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `cyValue`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `cyDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은에서 읽거나 쓸에서 참조를 변수에 `cyValue`를 적절 하 게 합니다. 경우 `cyDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_datapath"></a>PX_DataPath  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 데이터 경로 형식의 속성을 초기화 하는 함수 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)합니다.  
  
```  
 
BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    LPCTSTR 
pszPropName,  
    CDataPathProperty& dataPathProperty);

BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    CDataPathProperty& dataPathProperty);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `dataPathProperty`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 데이터 경로 속성 비동기 컨트롤 속성을 구현합니다. 속성의 값은에서 읽거나 쓸에서 참조를 변수에 `dataPathProperty`를 적절 하 게 합니다.  
  
##  <a name="px_double"></a>PX_Double  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 형식의 속성을 초기화 하는 함수 **이중**합니다.  
  
```  
 
BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& doubleValue);

BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& 
doubleValue  ,  
    double doubleDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `doubleValue`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `doubleDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나에서 참조 하는 변수를 쓸 `doubleValue`를 적절 하 게 합니다. 경우 `doubleDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_font"></a>PX_Font  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 직렬화 또는 글꼴의 속성을 초기화 합니다.  
  
```  
 
BOOL  
PX_Font(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CFontHolder& 
font  ,  
    const 
FONTDESC  
FAR* 
pFontDesc  
= 
NULL,  
    LPFONTDISP 
pFontDispAmbient  
= NULL);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `font`  
 에 대 한 참조는 `CFontHolder` 글꼴 속성을 포함 하는 개체입니다.  
  
 `pFontDesc`  
 에 대 한 포인터는 **FONTDESC** font 속성의 경우에서의 기본 상태로 초기화에 사용할 값을 포함 하는 구조를 `pFontDispAmbient` 는 **NULL**합니다.  
  
 `pFontDispAmbient`  
 에 대 한 포인터는 **IFontDisp** font 속성의 기본 상태로 초기화에 사용 하는 글꼴의 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나 쓴 `font`, `CFontHolder` 를 적절 한 참조입니다. 경우 `pFontDesc` 및 `pFontDispAmbient` 필요할 때 속성의 기본값을 초기화 하는 데 사용 하는 지정 됩니다. 이러한 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다. 일반적으로 전달 하면 **NULL** 에 대 한 `pFontDesc` 앰비언트 값을 반환 하 고 `COleControl::AmbientFont` 에 대 한 `pFontDispAmbient`합니다. 글꼴 개체에서 반환 하는 참고 `COleControl::AmbientFont` 를 호출 하 여 해제 되어야는 **IFontDisp::Release** 멤버 함수입니다.  
  
##  <a name="px_float"></a>PX_Float  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 형식의 속성을 초기화 하는 함수 **float**합니다.  
  
```  
 
BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& floatValue);

BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& 
floatValue  ,  
    float floatDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `floatValue`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `floatDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나에서 참조 하는 변수를 쓸 `floatValue`를 적절 하 게 합니다. 경우 `floatDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_iunknown"></a>PX_IUnknown  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 serialize 하거나 개체 함으로써 표시 되는 속성을 초기화 하는 **IUnknown**-파생 인터페이스입니다.  
  
```  
 
BOOL  
PX_IUnknown(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    LPUNKNOWN& 
pUnk  ,  
    REFIID 
iid  ,  
    LPUNKNOWN 
pUnkDefault  
= NULL);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 *pUnk*  
 속성의 값을 나타내는 개체의 인터페이스를 포함 하는 변수에 대 한 참조입니다.  
  
 `iid`  
 속성 개체의 인터페이스를 나타내는 인터페이스 ID는 컨트롤에 의해 사용 됩니다.  
  
 `pUnkDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나에서 참조 하는 변수를 쓸 *펑크*를 적절 하 게 합니다. 경우 `pUnkDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_long"></a>PX_Long  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 형식의 속성을 초기화 하는 함수 **긴**합니다.  
  
```  
 
BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& lValue);

BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& 
lValue  ,  
    long lDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `lValue`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `lDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나에서 참조 하는 변수를 쓸 `lValue`를 적절 하 게 합니다. 경우 `lDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_picture"></a>PX_Picture  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버 함수를 serialize 하거나 컨트롤의 사진 속성을 초기화 합니다.  
  
```  
 
BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& pict);

BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& 
pict  ,  
    CPictureHolder& pictDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `pict`  
 에 대 한 참조는 [CPictureHolder](../../mfc/reference/cpictureholder-class.md) 속성이 저장 된 개체 (일반적으로 클래스의 멤버 변수).  
  
 `pictDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나에서 참조 하는 변수를 쓸 `pict`를 적절 하 게 합니다. 경우 `pictDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_short"></a>PX_Short  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 형식의 속성을 초기화 하는 함수 **짧은**합니다.  
  
```  
 
BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& sValue);

BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& 
sValue  ,  
    short sDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `sValue`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `sDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나에서 참조 하는 변수를 쓸 `sValue`를 적절 하 게 합니다. 경우 `sDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_ulong"></a>PX_ULong  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 형식의 속성을 초기화 하는 함수 **ULONG**합니다.  
  
```  
 
BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& ulValue);

BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& 
ulValue  ,  
    long ulDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `ulValue`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `ulDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나에서 참조 하는 변수를 쓸 `ulValue`를 적절 하 게 합니다. 경우 `ulDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_ushort"></a>PX_UShort  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` 멤버를 serialize 하거나 형식의 속성을 초기화 하는 함수 `unsigned` **짧은**합니다.  
  
```  
 
BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& usValue);

BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& 
usValue  ,  
    USHORT usDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 *usValue*  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 *usDefault*  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나에서 참조 하는 변수를 쓸 *usValue*를 적절 하 게 합니다. 경우 *usDefault* 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_string"></a>PXstring  
 사용자 컨트롤 내에서이 함수를 호출 **DoPropExchange** 멤버 함수를 직렬화 또는 문자 문자열 속성을 초기화 합니다.  
  
```  
 
BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& strValue);

BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& 
strValue  ,  
    CString strDefault);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `strValue`  
 속성은 저장 된 변수에 대 한 참조 (일반적으로 클래스의 멤버 변수).  
  
 `strDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나에서 참조 하는 변수를 쓸 `strValue`를 적절 하 게 합니다. 경우 `strDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization 프로세스 어떤 이유로 든 실패 하는 경우 사용 합니다.  
  
##  <a name="px_vbxfontconvert"></a>PX_VBXFontConvert  
 사용자 컨트롤 내에서이 함수를 호출 `DoPropExchange` VBX 컨트롤의 글꼴 관련 속성을 변환 하 여 글꼴 속성을 초기화 하는 멤버 함수입니다.  
  
```  
 
BOOL  
PX_VBXFontConvert(
    CPropExchange* 
pPX  ,  
    CFontHolder& font);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPX`  
 에 대 한 포인터는 [CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체 (일반적으로에 대 한 매개 변수로 전달 된 `DoPropExchange`).  
  
 `font`  
 변환 된 VBX 글꼴 관련 속성을 포함 하는 OLE 컨트롤의 글꼴 속성입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 VBX 컨트롤에 대 한 직접 대용으로 디자인 된 OLE 컨트롤에 의해서만 사용 합니다. 컨트롤의 Visual Basic 개발 환경, 해당 교체 OLE 컨트롤을 사용 하 여 VBX 컨트롤을 포함 하는 form 변환할 때 호출 **IDataObject::SetData** VBX 컨트롤의 속성 데이터를 포함 하는 속성 집합을 전달 하는 함수입니다. 이 작업을이 수행 하면 컨트롤의 `DoPropExchange` 함수를 호출할 수 있습니다. `DoPropExchange`호출할 수 `PX_VBXFontConvert` VBX 컨트롤의 글꼴 관련 속성을 변환 하려면 (예를 들어 "FontName," "FontSize" 등) OLE 컨트롤의 글꼴 속성의 해당 구성 요소에 있습니다.  
  
 `PX_VBXFontConvert`컨트롤이 실제로 VBX 양식 응용 프로그램에서 변환할 때에 호출 해야 합니다. 예:  
  
 [!code-cpp[NVC_MFCActiveXControl #&14;](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]  
[!code-cpp[NVC_MFCActiveXControl #&15;](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

