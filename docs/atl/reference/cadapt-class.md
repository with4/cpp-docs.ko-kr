---
title: "CAdapt 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
dev_langs: C++
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4e565b1e2c20abf31919774d7bc6eb34f4c5f78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cadapt-class"></a>CAdapt 클래스
이 템플릿은 개체 주소 이외의 주소를 반환하도록 연산자 주소를 다시 정의하는 클래스를 래핑하는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class CAdapt
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 조정된 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAdapt::CAdapt](#cadapt)|생성자입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAdapt::operator const T &](#operator_const_t_amp)|`const`에 대한 `m_T` 참조를 반환합니다.|  
|[CAdapt::operator T &](#operator_t_amp)|`m_T`에 대한 참조를 반환합니다.|  
|[CAdapt::operator <](#operator_lt)|조정된 형식의 개체를 `m_T`와 비교합니다.|  
|[CAdapt::operator =](#operator_eq)|조정된 형식의 개체를 `m_T`에 할당합니다.|  
|[CAdapt::operator = =](#operator_eq_eq)|조정된 형식의 개체를 `m_T`와 비교합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAdapt::m_T](#m_t)|조정되는 데이터입니다.|  
  
## <a name="remarks"></a>설명  
 `CAdapt`연산자의 주소를 다시 정의 하는 클래스를 래핑하는 데 사용 하는 간단한 템플릿입니다 ( `operator &`) 개체의 주소 이외의 다른 결과를 반환 합니다. 이러한 클래스의 예로 ATL의 `CComBSTR`, `CComPtr`, `CComQIPtr` 클래스 및 컴파일러 COM 지원 클래스인 `_com_ptr_t`가 있습니다. 이러한 모든 클래스가 데이터 멤버 중 하나의 주소를 반환하도록 연산자 주소를 다시 정의합니다(`BSTR`의 경우 `CComBSTR` 및 기타 클래스의 경우 인터페이스 포인터).  
  
 `CAdapt`의 주요 역할은 클래스 `T`에서 정의된 연산자의 주소를 숨기지만 조정된 클래스의 특성을 유지하는 것입니다. `CAdapt`public 멤버를 보유 하 여이 역할을 fulfils [m_T](#m_t), 형식의 `T`, 및의 특수화를 허용 하도록 복사 생성자 및 변환 연산자, 비교 연산자를 정의 하 여 `CAdapt` 처럼 처리 형식의 개체 `T`합니다.  
  
 어댑터 클래스 `CAdapt`는 일부 컨테이너 스타일 클래스가 연산자 주소를 사용하여 포함된 개체의 주소를 가져올 수 있기 때문에 유용합니다. 연산자의 주소를 다시 정의하면 일반적으로 컴파일 오류가 발생하고 "작동"해야 하는 클래스에서 조정되지 않은 형식이 사용되지 않아 이 요구 사항에 맞지 않게 됩니다. `CAdapt`가 이러한 문제에 대한 해결 방법을 제공합니다.  
  
 일반적으로 컨테이너 스타일 클래스에 `CAdapt`, `CComBSTR`, `CComPtr` 또는 `CComQIPtr` 개체를 저장하려는 경우 `_com_ptr_t`를 사용합니다. 이는 C++11 표준이 지원되기 전에 C++ 표준 라이브러리 컨테이너에 대해 가장 일반적으로 필요했지만, 이제 C++11 표준 라이브러리 컨테이너가 `operator&()`를 오버로드한 형식으로 자동으로 작동합니다. 표준 라이브러리에서는이를 위해 내부적으로 사용 하 여 [std::addressof](../../standard-library/memory-functions.md#addressof) 개체의 실제 주소를 얻으려고 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcomcli.h  
  
##  <a name="cadapt"></a>CAdapt::CAdapt  
 생성자는 어댑터 개체를 생성, 조정 된 형식의 개체에서 복사 또는 다른 어댑터 개체에서 복사한 기본 수를 허용 합니다.  
  
```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>매개 변수  
 `rSrc`  
 새로 생성 된 개체에 복사 하도록 적용 된 형식의 변수입니다.  
  
 *rSrCA*  
 포함 된 데이터를 복사 (또는 이동할) 새로 생성 된 개체에는 어댑터 개체입니다.  
  
##  <a name="m_t"></a>CAdapt::m_T  
 조정 되는 데이터를 보유 합니다.  
  
```
T m_T;
```  
  
### <a name="remarks"></a>설명  
 이 **공용** 데이터 멤버와에 직접 또는 간접적으로 액세스할 수 [연산자 const T &](#operator_const_t_amp) 및 [연산자 T &](#operator_t_amp)합니다.  
  
##  <a name="operator_const_t_amp"></a>CAdapt::operator const T&amp;  
 반환 된 **const** 에 대 한 참조는 [m_T](#m_t) 형식의 개체인 것 처럼 처리를 어댑터 개체 멤버 `T`합니다.  
  
```  
operator const T&() const;
```  
  
### <a name="return-value"></a>반환 값  
 A **const** 에 대 한 참조 `m_T`합니다.  
  
##  <a name="operator_t_amp"></a>CAdapt::operator T&amp;  
 에 대 한 참조를 반환 합니다.는 [m_T](#m_t) 형식의 개체인 것 처럼 처리를 어댑터 개체 멤버 `T`합니다.  
  
```  
operator T&();
```     
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조 `m_T`합니다.  
  
##  <a name="operator_lt"></a>CAdapt::operator&lt;  
 와 조정 된 형식의 개체와 비교 [m_T](#m_t)합니다.  
  
```
bool operator<(const T& rSrc) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `rSrc`  
 비교할 개체에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 간의 비교 결과 `m_T` 및 `rSrc`합니다.  
  
##  <a name="operator_eq"></a>CAdapt::operator =  
 할당 연산자는 인수를 할당 `rSrc`, 데이터 멤버를 [m_T](#m_t) 현재 어댑터 개체를 반환 합니다.  
  
```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>매개 변수  
 `rSrc`  
 복사할 조정 된 형식의 개체에 대 한 참조입니다. 

 `rSrCA`개체를 이동할 수에 대 한 참조입니다. 
  
### <a name="return-value"></a>반환 값  
 현재 개체에 대 한 참조입니다.  
  
##  <a name="operator_eq_eq"></a>CAdapt::operator = =  
 와 조정 된 형식의 개체와 비교 [m_T](#m_t)합니다.  
  
```
bool operator== (const T& rSrc) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `rSrc`  
 비교할 개체에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 간의 비교 결과 `m_T` 및 `rSrc`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
