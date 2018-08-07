---
title: COleException 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs:
- C++
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 731ec7b359995fc8ecbfdeae89595442d8186eeb
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851394"
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
|[COleException::Process](#process)|OLE 반환 코드로 예외가 변환합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|예외에 대 한 이유를 나타내는 상태 코드를 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 `COleException` 클래스 예외 이유를 나타내는 상태 코드를 포함 하는 공용 데이터 멤버를 포함 합니다.  
  
 일반적으로 만들면 안을 `COleException` 개체 직접; 대신 호출 해야 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)합니다.  
  
 예외에 대 한 자세한 내용은 문서를 참조 하세요 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 하 고 [예외: OLE 예외](../../mfc/exceptions-ole-exceptions.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="m_sc"></a>  COleException::m_sc  
 이 데이터 멤버는 예외에 대 한 이유를 나타내는 OLE 상태 코드를 보유 합니다.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>설명  
 이 변수의 값을 설정한 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)합니다.  
  
 SCODE에 대 한 자세한 내용은 참조 하세요. [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK에 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>  COleException::Process  
 호출을 **프로세스** 멤버 함수는 예외가 OLE 상태 코드로 변환 합니다.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAnyException*  
 포착된 된 예외에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 OLE 상태 코드입니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 함수는 **정적**합니다.  
  
 SCODE에 대 한 자세한 내용은 참조 하세요. [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK에 있습니다.  
  
### <a name="example"></a>예  
  예를 참조 하세요 [coledispatchdriver:: Createdispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CALCDRIV MFC 샘플](../../visual-cpp-samples.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



