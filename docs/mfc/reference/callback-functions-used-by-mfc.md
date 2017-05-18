---
title: "MFC에서 사용 되는 콜백 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions, MFC
- MFC, callback functions
- functions [C++], callback
- callback functions
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
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
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: 08c6f547c95adb4c6794ec71259888d390e42e92
ms.contentlocale: ko-kr
ms.lasthandoff: 03/06/2017

---
# <a name="callback-functions-used-by-mfc"></a>MFC에서 사용하는 콜백 함수
세 가지 콜백 함수는 Microsoft Foundation 클래스 라이브러리에 표시 됩니다. 이러한 콜백 함수에 전달 됩니다 [cdc:: enumobjects](../../mfc/reference/cdc-class.md#enumobjects), [cdc:: graystring](../../mfc/reference/cdc-class.md#graystring), 및 [cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)합니다. 참고 모든 콜백 함수가 콜백 경계를 넘어 예외를 throw 할 수 있으므로 창에 반환 하기 전에 MFC 예외를 트래핑 해야 합니다. 예외에 대 한 자세한 내용은 문서를 참조 하십시오. [예외](../../mfc/exception-handling-in-mfc.md)합니다.  

|이름||  
|----------|-----------------|  
|[CDC::EnumObjects에 대한 콜백 함수](#enum_objects)||  
|[CDC::GrayString에 대한 콜백 함수](#graystring)||
|[CDC::SetAbortProc에 대한 콜백 함수](#setabortproc)|| 

## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h 

## <a name="enum_objects"></a>Cdc:: enumobjects에 대 한 콜백 함수
*ObjectFunc* 이름은 응용 프로그램 제공 하는 함수 이름에 대 한 자리 표시자입니다.  
  
### <a name="syntax"></a>구문  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszLogObject*  
 가리키는 [LOGPEN](../../mfc/reference/logpen-structure.md) 또는 [LOGBRUSH](../../mfc/reference/logbrush-structure.md) 개체의 논리적 특성에 대 한 정보를 포함 하는 데이터 구조입니다.  
  
 `lpData`  
 에 전달 되는 응용 프로그램에서 제공 하는 데이터를 가리키는 `EnumObjects` 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 콜백 함수는 반환 된 `int`합니다. 이 반환 값은 사용자 정의입니다. 콜백 함수는 0을 반환 하는 경우 `EnumObjects` 열거형 일찍 중지 합니다.  
  
### <a name="remarks"></a>주의  
 실제 이름을 내보내야 합니다.  
  
## <a name="graystring"></a>Cdc:: graystring에 대 한 콜백 함수
*OutputFunc* 응용 프로그램에서 제공 하는 콜백 함수 이름에 대 한 자리 표시자입니다.  
  
### <a name="syntax"></a>구문  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
### <a name="parameters"></a>매개 변수  
 `hDC`  
 최소한의 비트맵으로 메모리 장치 컨텍스트를 식별 너비와 높이에 지정 된 `nWidth` 및 `nHeight` 를 `GrayString`합니다.  
  
 `lpData`  
 그릴 문자열을 가리킵니다.  
  
 `nCount`  
 출력에 문자 수를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 콜백 함수의 반환 값 이어야 **TRUE** ; 성공을 나타내기 위해 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 콜백 함수 (*OutputFunc*) 좌표 (0,&0;)를 기준으로 이미지를 그리기 해야 하지 않고 (*x*, *y*).  

## <a name="setabortproc"></a>Cdc:: setabortproc에 대 한 콜백 함수
이름 *AbortFunc* 응용 프로그램 제공 하는 함수 이름에 대 한 자리 표시자입니다.  
  
### <a name="syntax"></a>구문  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
### <a name="parameters"></a>매개 변수  
 *hPr*  
 장치 컨텍스트를 식별합니다.  
  
 `code`  
 오류가 발생 했습니다 있는지 여부를 지정 합니다. 오류가 발생 하지 않은 경우 0입니다. **SP_OUTOFDISK** 인쇄 관리자가 현재 디스크 공간이 부족 하 고 더 많은 디스크 공간이 응용 프로그램이 대기 하는 경우에 사용할 수 있게 됩니다. 경우 `code` 는 **SP_OUTOFDISK**, 응용 프로그램에서 인쇄 작업을 중단할 필요가 없습니다. 그렇지 않으면이 반환 되어야 하며 인쇄 관리자에 게 호출 하 여는 **PeekMessage** 또는 **GetMessage** Windows 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 인쇄 작업을 계속 하면 0이 아니고 및 0 중단 처리기 함수의 반환 값이 취소 되는 경우.  
  
### <a name="remarks"></a>설명  
 설명 섹션에 설명 된 대로 실제 이름으로 내보내야 하며 [cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)합니다.  
 
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](structures-styles-callbacks-and-message-maps.md)
 [cdc:: enumobjects](../../mfc/reference/cdc-class.md#enumobjects)
 [cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)
 [cdc:: graystring](../../mfc/reference/cdc-class.md#graystring)


