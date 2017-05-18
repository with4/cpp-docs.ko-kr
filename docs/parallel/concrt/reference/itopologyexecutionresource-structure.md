---
title: "ITopologyExecutionResource 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d9671dbf84a1104bc3b6f3a6f9d383aac167759c
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource 구조체
리소스 관리자에 의해 정의된 실행 리소스에 대한 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```
struct ITopologyExecutionResource;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Itopologyexecutionresource:: Getid](#getid)|이 실행 리소스에 대한 리소스 관리자의 고유 식별자를 반환합니다.|  
|[Itopologyexecutionresource:: Getnext](#getnext)|열거 순서에서 다음 실행 리소스에 대한 인터페이스를 반환합니다.|  
  
## <a name="remarks"></a>주의  
 이 인터페이스는 일반적으로 리소스 관리자가 확인 되는 시스템의 토폴로지를 설명 하는 데 사용 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="getid"></a>Itopologyexecutionresource:: Getid 메서드  
 이 실행 리소스에 대한 리소스 관리자의 고유 식별자를 반환합니다.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 이 실행 리소스에 대한 리소스 관리자의 고유 식별자입니다.  
  
##  <a name="getnext"></a>Itopologyexecutionresource:: Getnext 메서드  
 열거 순서에서 다음 실행 리소스에 대한 인터페이스를 반환합니다.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 열거 순서에서 다음 실행 리소스에 대한 인터페이스입니다. 이 실행 리소스가 속한 노드의 열거 순서에 노드가 더 이상 없을 경우 이 메서드는 `NULL` 값을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)

