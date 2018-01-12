---
title: "Platform::Collections::BackInsertIterator 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
dev_langs: C++
helpviewer_keywords: BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 057aebfcba1936bc2a59fbb8b9fb51bff3197b6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Platform::Collections::BackInsertIterator 클래스
요소를 덮어쓰지 않고 순차 컬렉션의 백 엔드에 삽입하는 반복기를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <typename T>  
class BackInsertIterator : 
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 현재 컬렉션에 있는 항목의 형식입니다.  
  
### <a name="remarks"></a>설명  
 BackInsertIterator 클래스는 [back_insert_iterator Class](../standard-library/back-insert-iterator-class.md)에 필요한 규칙을 구현합니다.  
  
### <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Backinsertiterator:: Backinsertiterator](#ctor)|BackInsertIterator 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[BackInsertIterator::operator* 연산자](#operator-dereference)|현재 BackInsertIterator에 대한 참조를 검색합니다.|  
|[BackInsertIterator::operator++ 연산자](#operator-increment)|현재 BackInsertIterator에 대한 참조를 반환합니다. 반복기는 수정되지 않습니다.|  
|[BackInsertIterator::operator= 연산자](#operator-assign)|지정된 개체를 현재 순차 컬렉션의 끝에 추가합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `BackInsertIterator`  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
---
## <a name="ctor"></a>Backinsertiterator:: Backinsertiterator 생성자
`BackInsertIterator` 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
explicit BackInsertIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `v`  
 IVector\<T > 개체입니다.  
  
### <a name="remarks"></a>설명  
 `BackInsertIterator`는 `v` 매개 변수로 지정된 개체의 마지막 요소 뒤에 요소를 삽입합니다.  
 
## <a name="operator-assign"></a>Backinsertiterator:: Operator = 연산자
지정된 개체를 현재 순차 컬렉션의 끝에 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```    
BackInsertIterator& operator=( const T& t);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `t`  
 현재 컬렉션에 추가할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 BackInsertIterator에 대한 참조입니다.  

## <a name="operator-dereference"></a>Backinsertiterator:: Operator 연산자
현재 BackInsertIterator에 대한 참조를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BackInsertIterator& operator*();  
```  
  
### <a name="return-value"></a>반환 값  
 현재 BackInsertIterator에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 이 연산자는 현재 컬렉션의 요소가 아닌 현재 BackInsertIterator에 대한 참조를 반환합니다.  
 
## <a name="operator-increment"></a>Backinsertiterator:: Operator + + 연산자
현재 BackInsertIterator에 대한 참조를 반환합니다. 반복기는 수정되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
``` 
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(int);  
```  
  
### <a name="return-value"></a>반환 값  
 현재 BackInsertIterator에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 의도적으로, 첫 번째 구문 예는 현재 BackInsertIterator를 사전에 증가시키고 두 번째 구문은 현재 BackInsertIterator를 사후에 증가시킵니다. 두 번째 구문의 `int` 형식은 실제 정수 연산자가 아니라 후위 증가 연산을 나타냅니다.  
  
 그러나 이 연산자는 BackInsertIterator를 실제로 수정하지 않습니다. 대신에 수정되지 않은 현재 반복기에 대한 참조를 반환합니다. 이 같은 동작 [연산자 *](#dereference-operator)합니다.  
  
  
## <a name="see-also"></a>참고 항목  
 [플랫폼 Namespace](platform-namespace-c-cx.md)