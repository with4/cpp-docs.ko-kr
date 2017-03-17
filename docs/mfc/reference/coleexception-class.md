---
title: "COleException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs:
- C++
helpviewer_keywords:
- COleException class
- exceptions, OLE
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
caps.latest.revision: 22
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 059c92c8dc8796cf103cc02533ba5f3526720249
ms.lasthandoff: 02/24/2017

---
# <a name="coleexception-class"></a>COleException 클래스
OLE 작업과 관련된 예외 조건을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleException::Process](#process)|예외가 OLE 반환 코드로 변환합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|예외에 대 한 이유를 나타내는 상태 코드를 포함 합니다.|  
  
## <a name="remarks"></a>주의  
 `COleException` 클래스는 예외에 대 한 이유를 나타내는 상태 코드를 포함 하는 public 데이터 멤버를 포함 합니다.  
  
 일반적으로 만들면 안 한 `COleException` 개체 직접; 대신 호출 해야 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)합니다.  
  
 예외에 대 한 자세한 내용은 문서를 참조 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 및 [예외: OLE 예외](../../mfc/exceptions-ole-exceptions.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="m_sc"></a>COleException::m_sc  
 이 데이터 멤버는 예외에 대 한 이유를 나타내는 OLE 상태 코드를 보유 합니다.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>주의  
 이 변수 값을 설정한 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)합니다.  
  
 대 한 자세한 내용은 `SCODE`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&22;](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>COleException::Process  
 호출 된 **프로세스** 멤버 함수를 변환 OLE 상태 코드에 예외가 발생 했습니다.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAnyException*  
 포인터 예외가 발생 했습니다.  
  
### <a name="return-value"></a>반환 값  
 OLE 상태 코드입니다.  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  이 함수는 **정적**합니다.  
  
 대 한 자세한 내용은 `SCODE`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CALCDRIV](../../visual-cpp-samples.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




