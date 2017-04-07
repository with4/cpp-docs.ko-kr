---
title: "scoped_d3d_access_lock 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
dev_langs:
- C++
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: 8
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: fd7f377e1dfe4e99f566da4782be5c2ccfdddbff
ms.lasthandoff: 03/17/2017

---
# <a name="scopedd3daccesslock-class"></a>scoped_d3d_access_lock 클래스
D3D 액세스 잠금 accelerator_view 개체에 대 한 RAII 래퍼.  
  
### <a name="syntax"></a>구문  
  
```  
class scoped_d3d_access_lock;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[scoped_d3d_access_lock 생성자](#ctor)|오버로드됨. `scoped_d3d_access_lock` 개체를 생성합니다. 이 개체가 범위를 벗어날 때 잠금이 해제 됩니다.|  
|[~ scoped_d3d_access_lock 소멸자](#dtor)|연결된 된 D3D 액세스 잠금을 해제 `accelerator_view` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator=](#operator_eq)|다른 잠금에 대 한 소유권 `scoped_d3d_access_lock`합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `scoped_d3d_access_lock`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amprt.h  
  
 **Namespace:** concurrency:: direct3d  

##  <a name="ctor"></a>scoped_d3d_access_lock 

 `scoped_d3d_access_lock` 개체를 생성합니다. 이 개체가 범위를 벗어날 때 잠금이 해제 됩니다.  
 
```  
explicit scoped_d3d_access_lock(// [1] constructor  
    accelerator_view& _Av);

 
explicit scoped_d3d_access_lock(// [2] constructor  
    accelerator_view& _Av,  
    adopt_d3d_access_lock_t _T);

 
scoped_d3d_access_lock(// [3] move constructor  
    scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Av`  
 `accelerator_view` 잠금이 채택 합니다.  
  
 `_T`  
 `adopt_d3d_access_lock_t` 개체  
  
 `_Other`  
 `scoped_d3d_access_lock` 기존 잠금을 이동 될 개체입니다.  
  
## <a name="construction"></a>생성  
 [1] 생성자  
 에 D3D 액세스 잠금을 획득 하는 지정 된 [accelerator_view](accelerator-view-class.md) 개체. 생성은 잠금을 가져올 때까지 차단 됩니다.  
  
 [2] 생성자  
 D3D 액세스 잠금을 채택 하는 지정 된 [accelerator_view](accelerator-view-class.md) 개체입니다.  
  
 [3] 이동 생성자  
 다른 기존는 D3D 액세스 잠금이 `scoped_d3d_access_lock` 개체입니다. 생성을 차단 하지 않습니다.  

  
##  <a name="dtor"></a>~ scoped_d3d_access_lock 

 연결된 된 D3D 액세스 잠금을 해제 `accelerator_view` 개체입니다.  
  
```  
~scoped_d3d_access_lock();
```  
## <a name="operator_eq"></a>연산자 = 

다른 D3D 액세스 잠금에 대 한 소유권 `scoped_d3d_access_lock` 개체를 이전 잠금을 해제 합니다.  
 
```  
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 D3D 액세스 잠금을 이동 하려는 accelerator_view 합니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `scoped_accelerator_view_lock`합니다.  

## <a name="see-also"></a>참고 항목  
 [Concurrency::direct3d 네임스페이스](concurrency-direct3d-namespace.md)

