---
title: "CSimpleException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException class
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
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
ms.openlocfilehash: 5612d76a2351b9898b8ffe082844686d21fcd7a0
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
  
## <a name="remarks"></a>주의  
 `CSimpleException`리소스에 중요 한 MFC 예외에 대 한 기본 클래스 이며 소유권 및 오류 메시지의 초기화를 처리 합니다. 다음 클래스를 사용 하 여 `CSimpleException` 그 기본 클래스로:  
  
|||  
|-|-|  
|[CMemoryException 클래스](../../mfc/reference/cmemoryexception-class.md)|메모리 부족 예외|  
|[CNotSupportedException 클래스](../../mfc/reference/cnotsupportedexception-class.md)|지원 되지 않는 작업에 대 한 요청|  
|[CResourceException 클래스](../../mfc/reference/cresourceexception-class.md)|Windows 리소스를 찾을 수 없거나 불가|  
|[CUserException 클래스](../../mfc/reference/cuserexception-class.md)|리소스를 나타내는 예외를 찾을 수 없습니다.|  
|[CInvalidArgException 클래스](../../mfc/reference/cinvalidargexception-class.md)|잘못 된 인수를 나타내는 예외|  
  
 때문에 `CSimpleException` 되는 추상 기본 클래스를 선언할 수 없습니다는 `CSimpleException` 개체에 직접. 대신, 앞의 표에서 것과 같은 파생 된 개체를 선언 해야 합니다. 파생 된 클래스를 선언 하는 모델로 서 이전 클래스를 사용 합니다.  
  
 자세한 내용은 참조는 [CException 클래스](../../mfc/reference/cexception-class.md) 항목 및 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="csimpleexception"></a>CSimpleException::CSimpleException  
 생성자입니다.  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>매개 변수  
 `bAutoDelete`  
 지정 **TRUE** 하는 경우에 대 한 메모리는 `CSimpleException` 힙에 할당 된 개체입니다. 이 인해는 `CSimpleException` 삭제할 때 개체는 **삭제** 멤버 함수가 호출 되어 예외를 삭제 합니다. 지정 **FALSE** 경우는 `CSimpleException` 개체가 스택에 이거나 전역 개체입니다. 이 경우에 `CSimpleException` 개체는 되지 삭제는 **삭제** 멤버 함수를 호출 합니다.  
  
### <a name="remarks"></a>주의  
 되지 일반적으로이 생성자를 직접 호출 해야 합니다. 인스턴스를 만들어야 한다는 예외를 throw 하는 함수는 `CException`-파생 클래스와 MFC 중 하나를 사용 해야 함수 같은 throw 되거나 해당 생성자를 호출 [AfxThrowFileException](exception-processing.md#afxthrowfileexception), 미리 정의 된 형식을 throw 하 합니다.  
  
##  <a name="geterrormessage"></a>CSimpleException::GetErrorMessage  
 발생 한 오류에 대 한 텍스트를 제공 하려면이 멤버 함수를 호출 합니다.  
  
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
 버퍼에 저장할 수를 포함 한 문자의 최대 수는 **NULL** 종결자입니다.  
  
 `pnHelpContext`  
 주소는 **UINT** 는 받습니다 도움말 컨텍스트 id입니다. 경우 **NULL**, ID가 없습니다. 반환 됩니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0이 고 오류가 없으면 메시지 텍스트를 사용할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [예외 처리](../../mfc/exception-handling-in-mfc.md)




