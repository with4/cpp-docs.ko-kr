---
title: "표준 대화 상자 데이터 유효성 검사 루틴 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 87cf0389b7b58579a8674d4075d2601186b1ae95
ms.lasthandoff: 02/24/2017

---
# <a name="standard-dialog-data-validation-routines"></a>표준 대화 상자 데이터 유효성 검사 루틴
이 항목에서는 일반적인 MFC 대화 상자 컨트롤에 사용 되는 표준 대화 상자 데이터 유효성 검사 (DDV) 루틴을 나열 합니다.  
  
> [!NOTE]
>  표준 대화 상자 데이터 교환 루틴은 헤더 파일 afxdd_.h에 정의 됩니다. 그러나 응용 프로그램에는 afxwin.h를 포함 되어야 합니다.  
  
### <a name="ddv-functions"></a>DDV 함수  
  
|||  
|-|-|  
|[DDV_MaxChars](#ddv_maxchars)|지정 된 컨트롤 값의 문자 수가 지정된 된 최대를 초과 하지 않는 것을 확인 합니다.|  
|[DDV_MinMaxByte](#ddv_minmaxbyte)|지정 된 컨트롤 값을 초과 하지 않는 확인는 주어진 **바이트** 범위입니다.|  
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|지정 된 컨트롤 값을 특정된 시간 범위를 초과 하지 않는 것을 확인 합니다.|  
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|지정 된 컨트롤 값을 초과 하지 않도록 확인는 주어진 **double** 범위입니다.|  
|[DDV_MinMaxDWord](#ddv_minmaxdword)|지정 된 컨트롤 값을 초과 하지 않는 확인는 주어진 **DWORD** 범위입니다.|  
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|지정 된 컨트롤 값을 초과 하지 않는 확인는 주어진 **float** 범위입니다.|  
|[DDV_MinMaxInt](#ddv_minmaxint)|지정 된 컨트롤 값을 초과 하지 않는 확인는 주어진 **int** 범위입니다.|  
|[DDV_MinMaxLong](#ddv_minmaxlong)|지정 된 컨트롤 값을 초과 하지 않는 확인는 주어진 **긴** 범위입니다.|  
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|지정 된 컨트롤 값을 초과 하지 않는 확인는 주어진 **LONGLONG** 범위입니다.|  
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|지정 된 컨트롤 값을 지정된 된 날짜 범위를 초과 하지 않는 것을 확인 합니다.|  
|[DDV_MinMaxShort](#ddv_minmaxshort)|지정 된 컨트롤 값을 초과 하지 않는 확인는 주어진 **짧은** 범위입니다.|  
|[DDV_MinMaxSlider](#ddv_minmaxslider)|지정 된 슬라이더 컨트롤 값이 지정된 된 범위에 속하는지 확인 합니다.|  
|[DDV_MinMaxUInt](#ddv_minmaxuint)|지정 된 컨트롤 값을 초과 하지 않는 확인는 주어진 **UINT** 범위입니다.|  
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|지정 된 컨트롤 값을 초과 하지 않는 확인는 주어진 **ULONGLONG** 범위입니다.|  
  

  
##  <a name="a-nameddvmaxcharsa--ddvmaxchars"></a><a name="ddv_maxchars"></a>DDV_MaxChars  
 호출 `DDV_MaxChars` 컨트롤에 있는 문자의 크기 연관 확인 하려면 *값* 초과 하지 않는 *nChars*합니다.  
  
```   
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,  
    CString const& value,  
    int nChars); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `nChars`  
 최대 허용 문자 수입니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxbytea--ddvminmaxbyte"></a><a name="ddv_minmaxbyte"></a>DDV_MinMaxByte  
 호출 `DDV_MinMaxByte` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,  
    BYTE value,  
    BYTE minVal,  
    BYTE maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 **바이트**) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 **바이트**) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxdatetimea--ddvminmaxdatetime"></a><a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime  
 호출 `DDV_MinMaxDateTime` 컨트롤에서 날짜 및 시간 선택 날짜/시간 값을 확인 하려면 ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md))와 관련 된 *refValue* 사이 `refMinRange` 및 `refMaxRange`합니다.  
  
```   
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다. 이 개체를 삭제할 필요가 없습니다.  
  
 *refValue*  
 에 대 한 참조는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 또는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 대화 상자, 폼 보기 또는 컨트롤 뷰 개체의 멤버 변수를 연관 된 개체입니다. 이 개체는 데이터 유효성을 검사할 수를 포함 합니다.  
  
 `refMinRange`  
 최소 날짜/시간 값을 사용할 수 있습니다.  
  
 `refMaxRange`  
 허용 되는 최대 날짜/시간 값입니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxdoublea--ddvminmaxdouble"></a><a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble  
 호출 `DDV_MinMaxDouble` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,  
    double const& value,  
    double minVal,  
    double maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 **이중**) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 **이중**) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxdworda--ddvminmaxdword"></a><a name="ddv_minmaxdword"></a>DDV_MinMaxDWord  
 호출 `DDV_MinMaxDWord` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,  
    DWORD const& value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 `DWORD`) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 `DWORD`) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxfloata--ddvminmaxfloat"></a><a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat  
 호출 `DDV_MinMaxFloat` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,  
    float value,  
    float minVal,  
    float maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 **float**) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 **float**) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxinta--ddvminmaxint"></a><a name="ddv_minmaxint"></a>DDV_MinMaxInt  
 호출 `DDV_MinMaxInt` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,  
    int value,  
    int minVal,  
    int maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 `int`) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 `int`) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxlonga--ddvminmaxlong"></a><a name="ddv_minmaxlong"></a>DDV_MinMaxLong  
 호출 `DDV_MinMaxLong` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,  
    long value,  
    long minVal,  
    long maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 **긴**) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 **긴**) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxlonglonga--ddvminmaxlonglong"></a><a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong  
 호출 `DDV_MinMaxLongLong` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,  
    LONGLONG value,  
    LONGLONG minVal,  
    LONGLONG maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 **LONGLONG**) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 **LONGLONG**) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxmontha--ddvminmaxmonth"></a><a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth  
 호출 `DDV_MinMaxMonth` 컨트롤 월 달력에서 날짜/시간 값을 확인 하려면 ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md))와 관련 된 *refValue* 사이 `refMinRange` 및 `refMaxRange`합니다.  
  
```   
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *refValue*  
 형식의 개체에 대 한 참조 `CTime` 또는 `COleDateTime` 폼 보기, 또는 컨트롤 보기 개체 멤버 변수의 대화 상자에 연결 되어 있습니다. 이 개체는 데이터 유효성을 검사할 수를 포함 합니다. 이 참조의 경우 MFC 전달 `DDV_MinMaxMonth` 라고 합니다.  
  
 `refMinRange`  
 최소 날짜/시간 값을 사용할 수 있습니다.  
  
 `refMaxRange`  
 허용 되는 최대 날짜/시간 값입니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxshorta--ddvminmaxshort"></a><a name="ddv_minmaxshort"></a>DDV_MinMaxShort  
 호출 `DDV_MinMaxShort` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,  
    short value,  
    short minVal,  
    short maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 **짧은**) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 **짧은**) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxslidera--ddvminmaxslider"></a><a name="ddv_minmaxslider"></a>DDV_MinMaxSlider  
 호출 `DDV_MinMaxSlider` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,  
    DWORD value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 에 대 한 포인터는 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 유효성을 검사할 값에 대 한 참조입니다. 이 매개 변수를 보유 하거나 슬라이더 컨트롤의 현재 스크롤 상자 위치를 설정 합니다.  
  
 `minVal`  
 허용 되는 최소값입니다.  
  
 `maxVal`  
 허용 되는 최대값입니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 슬라이더 컨트롤에 대 한 정보를 참조 하십시오. [CSliderCtrl 사용 하 여](../../mfc/using-csliderctrl.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxuinta--ddvminmaxuint"></a><a name="ddv_minmaxuint"></a>DDV_MinMaxUInt  
 호출 `DDV_MinMaxUInt` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,  
    UINT value,  
    UINT minVal,  
    UINT maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 **UINT**) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 **UINT**) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
  
##  <a name="a-nameddvminmaxulonglonga--ddvminmaxulonglong"></a><a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong  
 호출 `DDV_MinMaxULongLong` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이 `minVal` 및 `maxVal`합니다.  
  
```   
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,  
    ULONGLONG value,  
    ULONGLONG  minVal ,  
    ULONGLONG  maxVal); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pDX`  
 `CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.  
  
 *value*  
 대화 상자, 폼 보기 또는 데이터는 유효성이 검사 된 컨트롤 뷰 개체의 멤버 변수에 대 한 참조입니다.  
  
 `minVal`  
 최소값 (형식의 **ULONGLONG**) 허용 합니다.  
  
 `maxVal`  
 최대값 (형식의 **ULONGLONG**) 허용 합니다.  
  
### <a name="remarks"></a>주의  
 DDV에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.  

### <a name="requirements"></a>요구 사항  
  **헤더** afxdd_.h  
    
## <a name="see-also"></a>참고 항목  
 [표준 대화 상자 데이터 교환 루틴](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

