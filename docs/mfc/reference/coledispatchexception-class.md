---
title: "COleDispatchException 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d90c59e4f85c871c113e51063ef1d50997bb508b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="coledispatchexception-class"></a>COleDispatchException 클래스
OLE 자동화의 핵심인 OLE `IDispatch` 인터페이스에만 해당하는 예외를 처리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleDispatchException : public CException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|오류에 대 한 도움말 컨텍스트입니다.|  
|[COleDispatchException::m_strDescription](#m_strdescription)|일반 언어로 된 오류 설명입니다.|  
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|도움말 파일을 사용 하면 `m_dwHelpContext`합니다.|  
|[COleDispatchException::m_strSource](#m_strsource)|예외를 생성 하는 응용 프로그램입니다.|  
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-특정 오류 코드입니다.|  
  
## <a name="remarks"></a>설명  
 마찬가지로 다른 예외 클래스에서 파생 되는 `CException` 기본 클래스 `COleDispatchException` 와 함께 사용할 수는 **THROW**, `THROW_LAST`, **시도**, **CATCH**, `AND_CATCH`, 및 `END_CATCH` 매크로입니다.  
  
 일반적으로 호출 해야 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) 만들고 throw 하는 `COleDispatchException` 개체입니다.  
  
 예외에 대 한 자세한 내용은 문서를 참조 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 및 [예외: OLE 예외](../../mfc/exceptions-ole-exceptions.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="m_dwhelpcontext"></a>COleDispatchException::m_dwHelpContext  
 응용 프로그램의 도움말의 도움말 컨텍스트를 식별 (합니다. HLP) 파일입니다.  
  
```  
DWORD m_dwHelpContext;  
```  
  
### <a name="remarks"></a>설명  
 이 멤버 함수에 의해 설정 되어 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) 때 예외가 throw 됩니다.  
  
### <a name="example"></a>예  
  예를 참조 [coledispatchdriver:: Createdispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)합니다.  
  
##  <a name="m_strdescription"></a>COleDispatchException::m_strDescription  
 "디스크가 꽉 찼습니다." 등의 일반 언어로 된 오류 설명을 포함합니다.  
  
```  
CString m_strDescription;  
```  
  
### <a name="remarks"></a>설명  
 이 멤버 함수에 의해 설정 되어 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) 때 예외가 throw 됩니다.  
  
### <a name="example"></a>예  
  예를 참조 [coledispatchdriver:: Createdispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)합니다.  
  
##  <a name="m_strhelpfile"></a>COleDispatchException::m_strHelpFile  
 응용 프로그램의 도움말 파일의 이름으로이 문자열의 프레임 워크를 채웁니다.  
  
```  
CString m_strHelpFile;  
```  
  
##  <a name="m_strsource"></a>COleDispatchException::m_strSource  
 프레임 워크 예외를 생성 하는 응용 프로그램의 이름으로이 문자열을 채웁니다.  
  
```  
CString m_strSource;  
```  
  
### <a name="example"></a>예  
  예를 참조 [coledispatchdriver:: Createdispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)합니다.  
  
##  <a name="m_wcode"></a>COleDispatchException::m_wCode  
 응용 프로그램에 오류 코드가 포함 되어 있습니다.  
  
```  
WORD m_wCode;  
```  
  
### <a name="remarks"></a>설명  
 이 멤버 함수에 의해 설정 되어 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) 때 예외가 throw 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CALCDRIV MFC 샘플](../../visual-cpp-samples.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDispatchDriver 클래스](../../mfc/reference/coledispatchdriver-class.md)   
 [COleException 클래스](../../mfc/reference/coleexception-class.md)
