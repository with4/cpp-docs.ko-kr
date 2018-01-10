---
title: "Platform:: array 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Array Constructors
- VCCORLIB/Namespace not found::Platform::Array::Value
dev_langs: C++
helpviewer_keywords: Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d7aa3a29615f6c744a3c790dd7b223225bc31f87
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="platformarray-class"></a>Platform::Array 클래스
ABI(응용 프로그램 이진 인터페이스)를 통해 받고 전달할 수 있는 수정 가능한 1차원 배열을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp    
template <typename T>  
private ref class Array<TArg, 1> :   
    public WriteOnlyArray<TArg, 1>,  
    public IBoxArray<TArg>   
```  
  
### <a name="members"></a>멤버  
 Platform:: array에서 모든 해당 메서드를 상속 [platform:: writeonlyarray 클래스](../cppcx/platform-writeonlyarray-class.md) 구현 하 고는 `Value` 의 속성은 [platform:: iboxarray 인터페이스](../cppcx/platform-iboxarray-interface.md)합니다.  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Array 생성자](#ctor)|클래스 템플릿 매개 변수에서 지정 된 형식의 수정 가능한 1 차원 배열을 초기화 *T*합니다.|  
  
### <a name="methods"></a>메서드  
 참조 [platform:: writeonlyarray 클래스](../cppcx/platform-writeonlyarray-class.md)합니다.  
  
### <a name="properties"></a>속성  
  
|||  
|-|-|  
|[Array:: value](#value)|현재 배열에 대한 핸들을 검색합니다.|  
  
### <a name="remarks"></a>설명  
 Array 클래스는 봉인되므로 상속할 수 없습니다.  
  
 Windows 런타임 형식 시스템 가변 배열의 개념이 지원 하지 않으며 따라서 IVector를 전달할 수 없습니다 < platform:: array\<T >> 반환 값 또는 메서드 매개 변수로 합니다. ABI 전반에서 가변 배열 또는 시퀀스의 시퀀스를 전달하려면 `IVector<IVector<T>^>`를 사용합니다.  
  
 시기 및 platform:: array를 사용 하는 방법에 대 한 자세한 내용은 참조 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)합니다.  
  
 Windows 런타임 형식 시스템 가변 배열의 개념이 지원 하지 않으며 따라서 IVector를 전달할 수 없습니다 < platform:: array\<T >> 반환 값 또는 메서드 매개 변수로 합니다. ABI 전반에서 가변 배열 또는 시퀀스의 시퀀스를 전달하려면 `IVector<IVector<T>^>`를 사용합니다.  
  
 이 클래스는 컴파일러가 자동으로 포함하는 vccorlib.h 헤더에 정의됩니다. platform.winmd에 정의된 public 형식이 아니기 때문에 개체 브라우저에는 표시되지 않지만 Intellisense에는 표시됩니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  

 
## <a name="ctor"></a>Array 생성자
클래스 템플릿 매개 변수에서 지정 된 형식의 수정 가능한 1 차원 배열을 초기화 *T*합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
Array(unsigned int size);  
Array(T* data, unsigned int size);    
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스 템플릿 매개 변수입니다.  
  
 `size`  
 배열의 요소 수입니다.  
  
 `data`  
 이 Array 개체를 초기화하는 데 사용되는 `T` 형식 데이터의 배열에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 Platform:: array 인스턴스를 만드는 방법에 대 한 자세한 내용은 참조 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)합니다.

## <a name="get"></a>Array:: get 메서드
지정된 인덱스 위치에서 배열 요소에 대한 참조를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp    
T& get(unsigned int index)  const;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `index`  
 배열에서 요소를 식별하는 0부터 시작하는 인덱스를 확인합니다. 최소 인덱스는 0이 고 최대 인덱스는 지정 된 값은 `size` 에서 매개 변수는 [배열 생성자](#ctor)합니다.  
  
### <a name="return-value"></a>반환 값  
 `index` 매개 변수로 지정된 배열 요소입니다.  
  
## <a name="value"></a>Array:: value 속성
현재 배열에 대한 핸들을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp 
property Array^ Value;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 배열에 대한 핸들입니다.  

## <a name="see-also"></a>참고 항목  
 [Platform 네임 스페이스](../cppcx/platform-namespace-c-cx.md)   
 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)