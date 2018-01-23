---
title: "Platform::Collections::VectorView 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
dev_langs: C++
helpviewer_keywords: VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 10619437ad7be96edb6ed2a0c4eb86c4f10580ca
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2018
---
# <a name="platformcollectionsvectorview-class"></a>Platform::Collections::VectorView 클래스
인덱스로 각각 액세스할 수 있는 순차 개체 컬렉션의 읽기 전용 보기를 나타냅니다. 템플릿 매개 변수로 지정된 컬렉션의 각 개체 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 `VectorView` 개체에 포함된 요소의 형식입니다.  
  
 `E`  
 `T`형식의 값을 사용하여 같음을 테스트하기 위한 이진 조건자를 지정합니다. 기본값은 `std::equal_to<T>`입니다.  
  
### <a name="remarks"></a>설명  
 `VectorView` 클래스가 구현 하는 [Windows::Foundation::Collections::IVectorView\<T >](http://go.microsoft.com/fwlink/p/?LinkId=262411) 인터페이스와 표준 템플릿 라이브러리 반복기에 대 한 지원.  
  
### <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[VectorView::VectorView](#ctor)|VectorView 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[VectorView::First](#first)|VectorView의 첫 번째 요소를 지정하는 반복기를 반환합니다.|  
|[VectorView::GetAt](#getat)|지정된 인덱스가 나타내는 현재 VectorView의 요소를 검색합니다.|  
|[VectorView::GetMany](#getmany)|현재 VectorView에서 지정된 인덱스부터 시작하여 일련의 항목을 검색합니다.|  
|[VectorView::IndexOf](#indexof)|현재 VectorView에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.|  
|[VectorView::Size](#size)|현재 VectorView 개체의 요소 수를 반환합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `VectorView`  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  

## <a name="first"></a>Vectorview:: First 메서드
VectorView의 첫 번째 요소를 지정하는 반복기를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
### <a name="return-value"></a>반환 값  
 VectorView의 첫 번째 요소를 지정하는 반복기입니다.  
  
### <a name="remarks"></a>설명  
 선언 된 변수에 반환 값을 할당 하는 First()에서 반환 된 반복기를 보유 하는 편리한 방법은 **자동** 형식 추론 키워드입니다. 예를 들어, `auto x = myVectorView->First();`을 입력합니다.  
  


## <a name="getat"></a>Vectorview:: Getat 메서드
지정된 인덱스가 나타내는 현재 VectorView의 요소를 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `index`  
 VectorView 개체의 특정 요소를 지정하는 0부터 시작하는 부호 없는 정수입니다.  
  
### <a name="return-value"></a>반환 값  
 `index` 매개 변수로 지정된 요소입니다. 요소 형식은 VectorView 템플릿 매개 변수로 지정 된 *T*합니다.  
  


## <a name="getmany"></a>Vectorview:: Getmany 메서드
현재 VectorView에서 지정된 인덱스부터 시작하여 일련의 항목을 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `startIndex`  
 검색할 항목 시작 부분의 0부터 시작하는 인덱스입니다.  
  
 `dest`  
 이 작업이 완료 될 때, 지정 된 요소에서 시작 하는 항목의 배열을 `startIndex` VectorView의 마지막 요소에서 끝나는 합니다.  
  
### <a name="return-value"></a>반환 값  
 검색된 항목의 수입니다.  
  


## <a name="indexof"></a>Vectorview:: Indexof 메서드
현재 VectorView에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `value`  
 찾을 항목입니다.  
  
 `index`  
 매개 변수 `value`가 있으면 0부터 시작하는 항목의 인덱스이고, 그렇지 않으면 0입니다.  
  
 항목이 VectorView의 첫 번째 요소이거나 항목을 찾을 수 없으면 `index` 매개 변수가 0입니다. 반환 값이 `true`일 경우 항목을 찾았고 첫 번째 요소인 것이며, 그렇지 않으면 항목을 찾지 못한 것입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 항목을 찾았으면 `true`이고, 그렇지 않으면 `false`입니다.  
  


## <a name="size"></a>Vectorview:: Size 메서드
현재 VectorView 개체의 요소 수를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 VectorView의 요소 수입니다.  
  


## <a name="ctor"></a>Vectorview:: Vectorview 생성자
VectorView 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `InIt`  
 현재 VectorView를 초기화하는 데 사용되는 개체 컬렉션의 형식입니다.  
  
 il  
 A [std:: initializer_list](../standard-library/initializer-list-class.md) 요소에서 VectorView를 초기화 하는 데 사용 됩니다.  
  
 `N`  
 현재 VectorView를 초기화하는 데 사용되는 개체 컬렉션의 요소 수입니다.  
  
 `size`  
 VectorView의 요소 수입니다.  
  
 `value`  
 현재 VectorView의 각 요소를 초기화하는 데 사용되는 값입니다.  
  
 `v`  
 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) 에 [std:: vector](../standard-library/vector-class.md) 현재 VectorView를 초기화 하는 데 사용 되는 합니다.  
  
 `ptr`  
 현재 VectorView를 초기화하는 데 사용되는 `std::vector`에 대한 포인터입니다.  
  
 `arr`  
 A [platform:: array](../cppcx/platform-array-class.md) 현재 VectorView를 초기화 하는 데 사용 되는 개체입니다.  
  
 `a`  
 A [std:: array](../standard-library/array-class-stl.md) 현재 VectorView를 초기화 하는 데 사용 되는 개체입니다.  
  
 `first`  
 현재 VectorView를 초기화하는 데 사용되는 개체 시퀀스의 첫 번째 요소입니다. 유형의 `first` 방법으로 전달 *완벽 전달*합니다. 자세한 내용은 [RValue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.  
  
 `last`  
 현재 VectorView를 초기화하는 데 사용되는 개체 시퀀스의 마지막 요소입니다. 유형의 `last` 방법으로 전달 *완벽 전달*합니다. 자세한 내용은 [RValue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.  
  


  
## <a name="see-also"></a>참고 항목  
 [플랫폼 Namespace](platform-namespace-c-cx.md)   
 [C + + Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)