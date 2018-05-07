---
title: CSimpleException 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d04a2f643add489d3302e58a9bde995303ecddd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="csimpleexception-class"></a>CSimpleException 클래스
이 클래스는 리소스에 중요한 MFC 예외의 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|발생 한 오류에 대 한 텍스트를 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 `CSimpleException` 리소스에 중요 한 MFC 예외에 대 한 기본 클래스 이며 소유권 및 오류 메시지의 초기화를 처리 합니다. 다음 사용 하는 클래스 `CSimpleException` 그 기본 클래스로:  
  
|||  
|-|-|  
|[CMemoryException 클래스](../../mfc/reference/cmemoryexception-class.md)|메모리 부족 예외|  
|[CNotSupportedException 클래스](../../mfc/reference/cnotsupportedexception-class.md)|지원 되지 않는 작업에 대 한 요청|  
|[CResourceException 클래스](../../mfc/reference/cresourceexception-class.md)|Windows 리소스를 찾을 수 없거나 불가|  
|[CUserException 클래스](../../mfc/reference/cuserexception-class.md)|리소스를 나타내는 예외를 찾을 수 없습니다.|  
|[CInvalidArgException 클래스](../../mfc/reference/cinvalidargexception-class.md)|잘못 된 인수를 나타내는 예외|  
  
 때문에 `CSimpleException` 는 추상 기본 클래스를 선언할 수 없습니다는 `CSimpleException` 개체를 직접 합니다. 대신, 이전 테이블에 있는 파생 된 개체를 선언 해야 합니다. 파생 된 클래스를 선언 하는 모델로 이전 클래스를 사용 합니다.  
  
 자세한 내용은 참조는 [CException 클래스](../../mfc/reference/cexception-class.md) 항목 및 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="csimpleexception"></a>  CSimpleException::CSimpleException  
 생성자입니다.  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>매개 변수  
 `bAutoDelete`  
 지정 **TRUE** 하는 경우에 대 한 메모리는 `CSimpleException` 힙에 할당 된 개체입니다. 이렇게 하면는 `CSimpleException` 삭제할 때 개체는 **삭제** 멤버 함수를 호출 하는 예외를 삭제 합니다. 지정 **FALSE** 경우는 `CSimpleException` 개체가 스택에 이거나 전역 개체입니다. 이 경우에 `CSimpleException` 됩니다 때는 **삭제** 멤버 함수를 호출 합니다.  
  
### <a name="remarks"></a>설명  
 이 생성자를 직접 호출 필요가 하는 것은 일반적으로 없습니다. 인스턴스를 만들도록 예외를 throw 하는 함수는 `CException`-파생 클래스와 MFC 중 하나를 사용 해야 함수 같은 throw 되거나 해당 생성자를 호출 [AfxThrowFileException](exception-processing.md#afxthrowfileexception), 미리 정의 된 형식이 throw 합니다.  
  
##  <a name="geterrormessage"></a>  CSimpleException::GetErrorMessage  
 발생 한 오류에 대 한 텍스트를 제공 하려면이 함수를 호출 합니다.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszError`  
 오류 메시지를 수신할 버퍼에 대 한 포인터입니다.  
  
 `nMaxError`  
 버퍼에 저장할 수를 포함 하 여 문자의 최대 수는 **NULL** 종결자입니다.  
  
 `pnHelpContext`  
 주소는 **UINT** 를 수신할 도움말 컨텍스트 id입니다. 경우 **NULL**, ID가 없습니다. 반환 됩니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않은 경우 없음 오류 메시지 텍스트에는 0 ´ ù.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [예외 처리](../../mfc/exception-handling-in-mfc.md)



