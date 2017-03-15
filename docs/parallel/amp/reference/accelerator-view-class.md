---
title: "accelerator_view 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator_view
dev_langs:
- C++
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: 18
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 78569f1ff21af3ed05cb908a851f0fe05d5d271a
ms.lasthandoff: 02/24/2017

---
# <a name="acceleratorview-class"></a>accelerator_view 클래스
C + + AMP 데이터 병렬 액셀러레이터에는 가상 장치 추상화를 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```  
class accelerator_view;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[accelerator_view 생성자](#ctor)|`accelerator_view` 클래스의 새 인스턴스를 초기화합니다.|  
|[~ accelerator_view 소멸자](#dtor)|소멸은 `accelerator_view` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[create_marker 메서드](#create_marker)|지금까지이 제출 된 모든 명령이 완료를 추적 하는 미래 반환 `accelerator_view` 개체입니다.|  
|[flush 메서드](#flush)|모든 보류 중인 명령은 큐에 대기 중인 전송에서 `accelerator_view` 실행을 위한 엑셀 러 레이 터에는 개체입니다.|  
|[get_accelerator 메서드](#get_accelerator)|`accelerator` 개체의 `accelerator_view` 개체를 반환합니다.|  
|[get_is_auto_selection 메서드](#get_is_auto_selection)|런타임에 적절 한 가속기가 자동으로 선택 여부를 나타내는 부울 값을 반환 하면는 `accelerator_view` 개체를 전달 하는 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)합니다.|  
|[get_is_debug 메서드](#get_is_debug)|나타내는 부울 값을 반환 여부는 `accelerator_view` 개체에 DEBUG 레이어가 확장 오류 보고에 대 한 활성화 합니다.|  
|[get_queuing_mode 메서드](#get_queuing_mode)|큐 모드를 반환 된 `accelerator_view` 개체입니다.|  
|[get_version 메서드](#get_version)|버전을 반환 된 `accelerator_view`합니다.|  
|[wait 메서드](#wait)|제출 된 모든 명령이 대기는 `accelerator_view` 완료 하는 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[연산자! = 연산자](#operator_neq)|비교 하 여 `accelerator_view` 반환 하 고 개체와 다른 `false` 않으면는 동일 합니다; 그렇지 않으면 반환 `true`합니다.|  
|[operator = 연산자](#operator_eq)|지정 된 내용을 복사 `accelerator_view` 을 여기에 개체입니다.|  
|[연산자 = = 연산자](#operator_eq_eq)|비교 하 여 `accelerator_view` 반환 하 고 개체와 다른 `true` 않으면는 동일 합니다; 그렇지 않으면 반환 `false`합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[accelerator 데이터 멤버](#accelerator)|`accelerator_view` 개체에 대한 `accelerator` 개체를 가져옵니다.|  
|[is_auto_selection 데이터 멤버](#is_auto_selection)|런타임에 적절 한 가속기가 자동으로 선택 여부를 나타내는 부울 값을 가져옵니다 때는 `accelerator_view` 개체를 전달 하는 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)합니다.|  
|[is_debug 데이터 멤버](#is_debug)|나타내는 부울 값을 가져옵니다 여부는 `accelerator_view` 개체에 DEBUG 레이어가 확장 오류 보고에 대 한 활성화 합니다.|  
|[queuing_mode 데이터 멤버](#queuing_mode)|큐 모드를 가져옵니다는 `accelerator_view` 개체입니다.|  
|[데이터 멤버 버전](#version)|가속기의 버전을 가져옵니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `accelerator_view`  
  
### <a name="remarks"></a>주의  
 `accelerator_view` 개체 액셀러레이터의 논리적이 고 격리 된 뷰를 나타냅니다. 단일 물리적 컴퓨팅 장치를 가질 수 있습니다 논리, 격리 된 `accelerator_view` 개체입니다. 각 엑셀 러 레이 터에는 기본 `accelerator_view` 개체입니다. 추가 `accelerator_view` 개체를 만들 수 있습니다.  
  
 물리적 장치를 많은 클라이언트 스레드 간에 공유할 수 있습니다. 클라이언트 스레드 수 공동으로 사용 하 여 동일한 `accelerator_view` 액셀러레이터 또는 각 클라이언트의 개체 독립을 통해 계산 장치와 통신할 수 `accelerator_view` 클라이언트 스레드에서를 격리 하는 개체입니다.  
  
 `accelerator_view` 개체 두 개 중 하나를 가질 수 [queuing_mode 열거형](concurrency-namespace-enums-amp.md#queuing_mode) 상태입니다. 큐 모드가 `immediate`, 같은 명령은 `copy` 및 `parallel_for_each` 호출자에 게 반환 되는 즉시 해당 가속기 장치에 전송 됩니다. 큐 모드가 `deferred`, 이러한 명령에 해당 하는 명령 큐에 대기 되며는 `accelerator_view` 개체입니다. 명령 될 때까지 장치를 실제로 전송 되지 않습니다 `flush()` 호출 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  

## <a name="a-nameacceleratora-accelerator"></a><a name="accelerator"></a>액셀러레이터 키 

Accelerator_view 개체에 대 한 엑셀 러 레이 터 개체를 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
## <a name="a-namectora-acceleratorview"></a><a name="ctor"></a>accelerator_view 

기존 복사 하 여 accelerator_view 클래스의 새 인스턴스를 초기화 `accelerator_view` 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
accelerator_view( const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 `accelerator_view` 복사할 개체입니다.  
  
## <a name="a-nameacceleratorviewcreatemarkera-createmarker"></a><a name="accelerator_view__create_marker"></a>create_marker 

지금까지이 제출 된 모든 명령이 완료를 추적 하는 미래 반환 `accelerator_view` 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
concurrency::completion_future create_marker();  
```  
  
### <a name="return-value"></a>반환 값  
 지금까지이 제출 된 모든 명령이 완료를 추적 하는 미래 `accelerator_view` 개체입니다.  
  
## <a name="a-nameflusha-flush"></a><a name="flush"></a>플러시 

Accelerator_view 개체 실행을 위한 엑셀 러 레이 터에 대기 중인 모든 보류 중인 명령을 제출 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void flush();  
```  
  
### <a name="return-value"></a>반환 값  
 `void`를 반환합니다.  

## <a name="a-nameacceleratorviewgetacceleratora-getaccelerator"></a><a name="accelerator_view__get_accelerator"></a>get_accelerator 

Accelerator_view 개체에 대 한 엑셀 러 레이 터 개체를 반환합니다.
### <a name="syntax"></a>구문
```
accelerator get_accelerator() const;
```
### <a name="return-value"></a>반환 값
Accelerator_view 개체에 대 한 엑셀 러 레이 터 개체입니다.

## <a name="a-nameacceleratorviewgetisautoselectiona-getisautoselection"></a><a name="accelerator_view__get_is_auto_selection"></a>get_is_auto_selection 

여부를 런타임에서 자동으로 선택 됩니다 적절 한 가속기는 accelerator_view로 전달 될 때를 나타내는 부울 값을 반환 된 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
bool get_is_auto_selection() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `true`런타임에서 적절 한 가속기; 자동으로 선택 하는 경우 그렇지 않으면 `false`합니다.  
  
## <a name="a-nameacceleratorviewgetisdebuga-getisdebug"></a><a name="accelerator_view__get_is_debug"></a>get_is_debug 

Accelerator_view 개체는 디버그 계층을 확장 오류 보고에 사용할 수 있는지 여부를 나타내는 부울 값을 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
bool get_is_debug() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `accelerator_view` 개체에 확장 오류 보고를 위해 DEBUG 레이어가 활성화되었는지 여부를 나타내는 부울 값입니다.  

## <a name="a-nameacceleratorviewgetqueuingmodea-getqueuingmode"></a><a name="accelerator_view__get_queuing_mode"></a>get_queuing_mode 

Accelerator_view 개체에 대 한 큐 모드를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```  
queuing_mode get_queuing_mode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `accelerator_view` 개체의 큐 모드입니다.  
  
## <a name="a-nameacceleratorviewgetversiona-getversion"></a><a name="accelerator_view__get_version"></a>get_version 

accelerator_view의 버전을 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
unsigned int get_version() const;  
```  
  
### <a name="return-value"></a>반환 값  
 버전은 `accelerator_view`합니다.  
  
## <a name="a-nameacceleratorviewisautoselectiona-isautoselection"></a><a name="accelerator_view__is_auto_selection"></a>is_auto_selection 

여부를 런타임에서 자동으로 선택 됩니다 적절 한 가속기는 accelerator_view로 전달 될 때를 나타내는 부울 값을 가져옵니다는 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
## <a name="a-nameacceleratorviewisdebuga-isdebug"></a><a name="accelerator_view__is_debug"></a>is_debug 

Accelerator_view 개체는 디버그 계층을 확장 오류 보고에 사용할 수 있는지 여부를 나타내는 부울 값을 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
## <a name="a-nameacceleratorviewoperatorneqa-operator"></a><a name="accelerator_view__operator_neq"></a>연산자! = 

이 accelerator_view 개체와 다른 비교 하 고 반환 `false` 않으면는 동일 합니다; 그렇지 않으면 반환 `true`합니다.  
  
### <a name="syntax"></a>구문  
  
```  
bool operator!= (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 이것과 비교할 `accelerator_view` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 두 개체가 같으면 `false`이고, 그렇지 않으면 `true`입니다.  
  
## <a name="a-nameacceleratorviewoperatoreqa-operator"></a><a name="accelerator_view__operator_eq"></a>연산자 = 

지정 된 accelerator_view 개체의 내용을 여기로 복사합니다.  
  
### <a name="syntax"></a>구문  
  
```  
accelerator_view & operator= (    const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 `accelerator_view` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 수정된 `accelerator_view` 개체에 대한 참조입니다.  
  
## <a name="a-nameacceleratorviewoperatoreqeqa-operator"></a><a name="accelerator_view__operator_eq_eq"></a>연산자 = = 

이 accelerator_view 개체와 다른 비교 하 고 반환 `true` 않으면는 동일 합니다; 그렇지 않으면 반환 `false`합니다.  
  
### <a name="syntax"></a>구문  
  
```  
bool operator= = (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 이것과 비교할 `accelerator_view` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 두 개체가 같으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="a-nameacceleratorviewqueuingmodea-queuingmode"></a><a name="accelerator_view__queuing_mode"></a>queuing_mode 

Accelerator_view 개체에 대 한 큐 모드를 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
## <a name="a-nameacceleratorviewversiona-version"></a><a name="accelerator_view__version"></a>버전 

accelerator_view의 버전을 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
## <a name="a-nameacceleratorviewwaita-wait"></a><a name="accelerator_view__wait"></a>대기 

끝나기를 accelerator_view 개체에 제출 된 모든 명령이 대기 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void wait();  
```  
  
#### <a name="return-value"></a>반환 값  
 `void`를 반환합니다.  
  
#### <a name="remarks"></a>주의  
 하는 경우는 [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) 는 `immediate`,이 메서드는 블로킹 없이 즉시 반환 합니다.  
  
##  <a name="a-namedtora-acceleratorview"></a><a name="dtor"></a>~ accelerator_view 

 Accelerator_view 개체를 소멸 시킵니다.  
  
#### <a name="syntax"></a>구문  
  
```  
~accelerator_view();  
```  
  
### <a name="return-value"></a>반환 값  
  
 
## <a name="see-also"></a>참고 항목  
 [동시성 Namespace (c + + AMP)](concurrency-namespace-cpp-amp.md)

