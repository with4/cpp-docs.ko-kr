---
title: "CResourceException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CResourceException
dev_langs:
- C++
helpviewer_keywords:
- resource allocation exception
- resources [C++], allocating
- resource exceptions
- exceptions, resource
- CResourceException class
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2013a73f91687277df9dd1e6747aba2dd02a4346
ms.lasthandoff: 02/24/2017

---
# <a name="cresourceexception-class"></a>CResourceException 클래스
Windows에서 요청된 리소스를 찾거나 할당할 수 없을 경우 발생합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CResourceException : public CSimpleException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CResourceException::CResourceException](#cresourceexception)|`CResourceException` 개체를 생성합니다.|  
  
## <a name="remarks"></a>주의  
 더 이상 없는 한정 가능한 것은 필요 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CResourceException`, 문서를 참조 하십시오 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="a-namecresourceexceptiona--cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a>CResourceException::CResourceException  
 `CResourceException` 개체를 생성합니다.  
  
```  
CResourceException();
```  
  
### <a name="remarks"></a>주의  
 이 생성자를 직접 사용 하지 않고 대신 전역 함수를 호출 [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)합니다. 예외에 대 한 자세한 내용은 문서를 참조 하십시오. [MFC의 예외 처리](../exception-handling-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](cexception-class.md)   
 [계층 구조 차트](../hierarchy-chart.md)



