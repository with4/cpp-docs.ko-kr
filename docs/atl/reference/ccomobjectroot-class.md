---
title: "CComObjectRoot 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
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
translationtype: Machine Translation
ms.sourcegitcommit: 31295a07704e272799398aa82c6a9f0bbac17717
ms.openlocfilehash: 34653d55091a8e872f075010a0ef7cecbb3484c8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectroot-class"></a>CComObjectRoot 클래스
이 형식 정의의 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) 스레딩 모델이 서버의 기본에 템플릿 화 됩니다.  
  
## <a name="syntax"></a>구문  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>주의  
 `CComObjectRoot`한 `typedef` 의 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) 스레딩 모델이 서버의 기본에 템플릿 화 됩니다. 따라서 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 중 하나를 참조 합니다 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)합니다.  
  
 `CComObjectRootEx`집계 및 집계 된 개체에 대 한 개체 참조 개수 관리를 처리합니다. 개체가 집계 되는 개체를 집계 하는 경우 알 수 없는 외부에 포인터를 보유 하는 경우 개체 참조 횟수를 보유 합니다. 집계 개체에 대 한 `CComObjectRootEx` 메서드는 내부 개체를 생성 하는 오류 처리를 사용할 수 있습니다 하 고 내부 인터페이스 릴리스될 때 삭제 되지 않도록에서 외부 개체 또는 내부 개체를 보호 하기 위해 삭제 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
## <a name="see-also"></a>참고 항목  
 [CComObjectRootEx 클래스 멤버](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)   
 [CComObject 클래스](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

