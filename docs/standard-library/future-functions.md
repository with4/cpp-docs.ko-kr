---
title: "&lt;future&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: d136f972786938e453d5a9116ea198ac2a5d8f46
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ltfuturegt-functions"></a>&lt;future&gt; 함수
||||  
|-|-|-|  
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|  
|[make_error_condition](#make_error_condition)|[swap](#swap)|  
  
##  <a name="async"></a>  async  
 *비동기 공급자*를 나타냅니다.  
  
```
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```  
  
### <a name="parameters"></a>매개 변수  
 `policy`  
 [launch](../standard-library/future-enums.md#launch) 값입니다.  
  
### <a name="remarks"></a>설명  
 약어의 정의:  
  
|||  
|-|-|  
|*dfn*|호출하는 `decay_copy(forward<Fn>(fn))`의 결과입니다.|  
|*dargs*|`decay_copy(forward<ArgsTypes>(args...))` 호출의 결과입니다.|  
|*Ty*|`result_of<Fn(ArgTypes...)>::type` 형식|  
  
 첫 번째 템플릿 함수는 `async(launch::any, fn, args...)`를 반환합니다.  
  
 두 번째 함수는 *연결된 비동기 상태*에 *dfn* 및 *dargs*의 값과 결과를 갖는 `future<Ty>` 개체와, 개별 스레드 실행을 관리하는 스레드 개체를 반환합니다.  
  
 `decay<Fn>::type`이 시작 이외의 형식이 아닌 경우 두 번째 함수는 오버로드 확인에 참여하지 않습니다.  
  
 `policy`가 `launch::any`인 경우 함수는 `launch::async` 또는 `launch::deferred`를 선택합니다. 이 구현에서는 함수는 `launch::async`를 사용합니다.  
  
 `policy`가 `launch::async`인 경우 함수는 `INVOKE(dfn, dargs..., Ty)`를 계산하는 스레드를 생성합니다. 함수는 결과를 기다리지 않고 스레드를 만든 후 반환합니다. 시스템에서 새 스레드를 시작할 수 없으면 오류 코드가 `resource_unavailable_try_again`인 [system_error](../standard-library/system-error-class.md)를 throw합니다.  
  
 `policy`가 `launch::deferred`일 경우 연결된 비동기 상태에 *지연된 함수*가 있는 것으로 표시하고 반환합니다. 연결된 비동기 상태가 유효해지기를 기다리는 non-timed 함수의 첫 번째 호출은 `INVOKE(dfn, dargs..., Ty)`를 평가함으로써 지연된 함수를 호출합니다.  
  
 어떤 경우에도 `future` 개체의 연결된 비동기 상태는 예외를 throw하거나 정상적으로 반환함으로써 `INVOKE(dfn, dargs..., Ty)`의 계산이 완료될 때까지 *준비*로 설정되지 않습니다. 예외가 throw되거나 계산에서 값이 반환된 경우 연결된 비동기 상태의 결과는 예외입니다.  
  
> [!NOTE]
>  `std::async`로 시작하는 작업에 연결된 `future` 또는 마지막 [shared_future](../standard-library/shared-future-class.md)의 경우 작업이 완료되지 않은 경우 소멸자가 차단됩니다. 즉 이 스레드가 `.get()` 또는 `.wait()`를 아직 호출하지 않은 경우 소멸자를 차단하고 작업을 계속 실행합니다. `future`에서 가져온 `std::async`가 로컬 범위 밖으로 이동되는 경우 해당 future를 사용하는 다른 코드는 공유 상태 준비를 위해 소멸자가 차단될 것을 알고 있어야 합니다.  
  
 의사 함수 `INVOKE`는 [\<functional>](../standard-library/functional.md)에 정의되어 있습니다.  
  
##  <a name="future_category"></a>  future_category  
 `future` 개체와 연결된 오류의 특징을 결정하는 [error_category](../standard-library/error-category-class.md) 개체에 대한 참조를 반환합니다.  
  
```
const error_category& future_category() noexcept;
```  
  
##  <a name="make_error_code"></a>  make_error_code  
 [future](../standard-library/future-class.md) 오류의 특징을 결정하는 [error_category](../standard-library/error-category-class.md) 개체와 함께 [error_code](../standard-library/error-code-class.md)를 만듭니다.  
  
```
inline error_code make_error_code(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>매개 변수  
 `Errno`  
 보고된 오류를 식별하는 [future_errc](../standard-library/future-enums.md#future_errc) 값입니다.  
  
### <a name="return-value"></a>반환 값  
 `error_code(static_cast<int>(Errno), future_category());`  
  
##  <a name="make_error_condition"></a>  make_error_condition  
 [future](../standard-library/future-class.md) 오류의 특정을 결정하는 [error_category](../standard-library/error-category-class.md) 개체와 함께 [error_condition](../standard-library/error-condition-class.md)을 만듭니다.  
  
```
inline error_condition make_error_condition(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>매개 변수  
 `Errno`  
 보고된 오류를 식별하는 [future_errc](../standard-library/future-enums.md#future_errc) 값입니다.  
  
### <a name="return-value"></a>반환 값  
 `error_condition(static_cast<int>(Errno), future_category());`  
  
##  <a name="swap"></a>  swap  
 `promise` 개체 하나의 *연결된 비동기 상태*를 다른 개체의 상태와 교환합니다.  
  
```
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `promise` 개체입니다.  
  
 `Right`  
 오른쪽 `promise` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<future>](../standard-library/future.md)



