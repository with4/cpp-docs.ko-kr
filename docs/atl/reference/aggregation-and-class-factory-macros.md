---
title: "집계 및 클래스 팩터리 매크로 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4509f7be36e45cf96a938e30ec0f82ec0c9836b5
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="aggregation-and-class-factory-macros"></a>집계 및 클래스 팩터리 매크로
이러한 매크로는 클래스 팩터리를 선언 하 고 집계를 제어 하는 방법을 제공 합니다.  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|선언 개체가 될 수 있습니다 (기본값)를 집계 합니다.|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|클래스 팩터리 되도록 선언 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ATL 기본 클래스 팩터리입니다.|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|클래스 팩터리를 클래스 팩터리 개체를 선언 합니다.|  
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|선언 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) 클래스 팩터리 되도록 합니다.|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|선언 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리 되도록 합니다.|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|선언 [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) 클래스 팩터리 되도록 합니다.|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|가상 선언 `GetControllingUnknown` 함수입니다.|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|개체를 집계할 수 없는 선언 합니다.|  
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|개체를 집계 되어야 합니다 선언 합니다.|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|알 수 없는 외부의 값을 확인 하 고 집계할 수 또는 집계할 수 없는 적절 하 게 개체를 선언 합니다.|  
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|외부 개체는 내부 개체를 생성 하는 동안 삭제 되지 않도록에서 보호합니다.|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|지정 된 **상태 보기** 컨테이너에 대 한 플래그입니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
   
##  <a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE  
 개체를 집계할 수 있도록 지정 합니다.  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 집계할 수로 정의 하는 클래스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 기본 집계 모델을 지정 하려면이 매크로 포함 합니다. 이 기본값을 재정의 하려면는 [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) 또는 [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) 클래스 정의에 매크로입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_classfactory"></a>DECLARE_CLASSFACTORY  
 선언 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 클래스 팩터리 되도록 합니다.  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>주의  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 이 매크로 사용 하 여 개체에 대 한 기본 클래스 팩터리를 선언할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#55;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="ccomclassfactory_class"></a>CComClassFactory 클래스  
 이 클래스를 구현 하는 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) 인터페이스입니다.  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>주의  
 `CComClassFactory`구현 하는 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) 인터페이스를 위한 새 개체를 보다 신속 하 게 만들 수 있도록 메모리에서 클래스 팩터리 잠금 수 있을 뿐만 아니라 특정 CLSID의 개체를 만드는 메서드를 포함 합니다. **IClassFactory** 시스템 레지스트리에 및 CLSID을 할당할를 등록 하는 모든 클래스에 대해 구현 해야 합니다.  
  
 ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로가 포함 [DECLARE_CLASSFACTORY](#declare_classfactory)를 선언 하 `CComClassFactory` 기본 클래스 팩터리로 합니다. 이 기본값을 재정의 하려면 중 하나를 지정 된 `DECLARE_CLASSFACTORY` *XXX* 클래스 정의에 매크로입니다. 예를 들어는 [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) 매크로 클래스 팩터리에 대 한 지정된 된 클래스를 사용 합니다.  
  
 [!code-cpp[NVC_ATL_COM&#8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 위의 클래스 정의 지정 하는 **CMyClassFactory** 개체의 기본 클래스 팩터리로 사용 됩니다. **CMyClassFactory** 에서 파생 되어야 `CComClassFactory` 시키고 `CreateInstance`합니다.  
  
 ATL은 클래스 팩터리를 선언 하는 세 가지 매크로 제공:  
  
- [DECLARE_CLASSFACTORY2](#declare_classfactory2) 사용 하 여 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), 컨트롤 라이선스를 통해 생성 됩니다.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) 사용 하 여 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)는 여러 아파트에서 개체를 만듭니다.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) 사용 하 여 [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)를 생성 하는 단일 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체입니다.  
  
##  <a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX  
 선언 `cf` 클래스 팩터리 되도록 합니다.  
  
```
DECLARE_CLASSFACTORY_EX( cf )
```  
  
### <a name="parameters"></a>매개 변수  
 `cf`  
 [in] 클래스 팩터리 개체를 구현 하는 클래스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 `cf` 매개 변수에서 파생 되어야 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 재정의 `CreateInstance` 메서드.  
  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_CLASSFACTORY](#declare_classfactory) 지정 하는 매크로 `CComClassFactory` 기본 클래스 팩터리로 합니다. 그러나 포함 하 여는 `DECLARE_CLASSFACTORY_EX` 매크로 개체의 클래스 정의에서이 기본값을 재정의 하면 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2  
 선언 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) 클래스 팩터리 되도록 합니다.  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>매개 변수  
 *-사용권 계약*  
 [in] 구현 하는 클래스 `VerifyLicenseKey`, `GetLicenseKey`, 및 `IsLicenseValid`합니다.  
  
### <a name="remarks"></a>주의  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_CLASSFACTORY](#declare_classfactory) 지정 하는 매크로 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 그러나 포함 하 여는 `DECLARE_CLASSFACTORY2` 매크로 개체의 클래스 정의에서이 기본값을 재정의 하면 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
##  <a name="ccomclassfactory2_class"></a>CComClassFactory2 클래스  
 이 클래스를 구현 하는 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) 인터페이스입니다.  
  
```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```    
  
### <a name="parameters"></a>매개 변수  
 *라이선스*  
 다음과 같은 정적 함수를 구현 하는 클래스:  
  
- **정적 BOOL VerifyLicenseKey (BSTR** `bstr` **);**  
  
- **정적 BOOL GetLicenseKey (DWORD** `dwReserved` **를 BSTR\* ** `pBstr` **);**  
  
- **정적 BOOL IsLicenseValid ();**  
  
### <a name="remarks"></a>주의  
 `CComClassFactory2`구현 하는 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) 확장 인터페이스의 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)합니다. **IClassFactory2** 컨트롤 개체는 라이선스를 통해 생성 됩니다. 클래스 팩터리를 실행 하는 사용이 허가 된 컴퓨터에서 런타임 라이선스 키를 제공할 수 있습니다. 이 라이선스 키에는 응용을 프로그램을 전체 컴퓨터 라이선스 존재 하지 않을 경우 개체를 인스턴스화할 수 있습니다.  
  
 ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로가 포함 [DECLARE_CLASSFACTORY](#declare_classfactory)를 선언 하 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 사용 하 여 `CComClassFactory2`, 지정는 [DECLARE_CLASSFACTORY2](#declare_classfactory2) 개체의 클래스 정의에 매크로입니다. 예:  
  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 **CMyLicense**, 템플릿 매개 변수를 `CComClassFactory2`, 정적 함수를 구현 해야 `VerifyLicenseKey`, `GetLicenseKey`, 및 `IsLicenseValid`합니다. 다음은 간단한 라이선스 클래스의 예입니다.  
  
 [!code-cpp[NVC_ATL_COM&#3;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2`둘 다에서 파생 되며 **CComClassFactory2Base** 및 *라이선스*합니다. **CComClassFactory2Base**에서 파생 됩니다, **IClassFactory2** 및 **CComObjectRootEx\< CComGlobalsThreadModel >**합니다.  
  
##  <a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD  
 선언 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리 되도록 합니다.  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>주의  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_CLASSFACTORY](#declare_classfactory) 지정 하는 매크로 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 그러나 포함 하 여는 `DECLARE_CLASSFACTORY_AUTO_THREAD` 매크로 개체의 클래스 정의에서이 기본값을 재정의 하면 됩니다.  
  
 (프로세싱 아웃 서버)에서 여러 아파트에서 개체를 만들 때 추가 `DECLARE_CLASSFACTORY_AUTO_THREAD` 클래스에 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="ccomclassfactoryautothread_class"></a>CComClassFactoryAutoThread 클래스  
 이 클래스를 구현 하는 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) , 인터페이스 및 개체를 여러 아파트에서 만들 수 있습니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>주의  
 `CComClassFactoryAutoThread`유사한 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), 개체를 여러 아파트에서 만들 수 있습니다. 이 지원을 활용 하 여 EXE 모듈에서 파생 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다.  
  
 ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로가 포함 [DECLARE_CLASSFACTORY](#declare_classfactory)를 선언 하 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 사용 하 여 `CComClassFactoryAutoThread`, 지정는 [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) 개체의 클래스 정의에 매크로입니다. 예:  
  
 [!code-cpp[NVC_ATL_COM&#9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON  
 선언 [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) 클래스 팩터리 되도록 합니다.  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>매개 변수  
 `obj`  
 [in] 클래스 개체의 이름입니다.  
  
### <a name="remarks"></a>주의  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_CLASSFACTORY](#declare_classfactory) 지정 하는 매크로 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 그러나 포함 하 여는 `DECLARE_CLASSFACTORY_SINGLETON` 매크로 개체의 클래스 정의에서이 기본값을 재정의 하면 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="ccomclassfactorysingleton_class"></a>CComClassFactorySingleton 클래스  
 이 클래스에서 파생 되며 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 단일 개체를 구성할 수 있습니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 클래스입니다.  
  
 `CComClassFactorySingleton`파생 되며 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 단일 개체를 구성할 수 있습니다. 각 호출에는 `CreateInstance` 메서드는 단순히이 개체는 인터페이스 포인터를 쿼리 합니다.  
  
### <a name="remarks"></a>주의  
 ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로가 포함 [DECLARE_CLASSFACTORY](#declare_classfactory)를 선언 하 `CComClassFactory` 기본 클래스 팩터리로 합니다. 사용 하 여 `CComClassFactorySingleton`를 지정 된 [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) 개체의 클래스 정의에 매크로입니다. 예:  
  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN  
 가상 함수를 선언 `GetControllingUnknown`합니다.  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>주의  
 컴파일러 오류 메시지를 가져올 경우 개체에이 매크로 추가 `GetControllingUnknown` 정의 되지 않습니다 (예를 들어, **CComAggregateCreator**).  
  
##  <a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE  
 개체를 집계할 수 없는 지정 합니다.  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 집계할 수 없는 것으로 정의 하는 클래스 개체의 이름입니다.  
  
### <a name="remarks"></a>주의  
 `DECLARE_NOT_AGGREGATABLE`로 인해 `CreateInstance` 오류를 반환 ( **CLASS_E_NOAGGREGATION**) 하려고 하는 경우 개체에 대 한 집계를 합니다.  
  
 기본적으로 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함는 [DECLARE_AGGREGATABLE](#declare_aggregatable) 개체를 집계할 수 있도록 지정 하는 매크로입니다. 이 기본 동작을 재정의 하려면 포함 `DECLARE_NOT_AGGREGATABLE` 클래스 정의에 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE  
 개체 해야 집계할 수 있도록 지정 합니다.  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 만 집계할 수로 정의 하는 클래스 개체의 이름입니다.  
  
### <a name="remarks"></a>주의  
 `DECLARE_ONLY_AGGREGATABLE`오류 발생 ( **E_FAIL**) 하려고 시도 하는 경우 **CoCreate** 집계 되지 않은 원시 개체로 개체입니다.  
  
 기본적으로 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함는 [DECLARE_AGGREGATABLE](#declare_aggregatable) 개체를 집계할 수 있도록 지정 하는 매크로입니다. 이 기본 동작을 재정의 하려면 포함 `DECLARE_ONLY_AGGREGATABLE` 클래스 정의에 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&125;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE  
 지정 하는 인스턴스의 **CComPolyObject \< ** *x* ** > ** 개체를 만들 때 만들어집니다.  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 집계할 수 또는 집계할 수 없는으로 정의 하는 클래스 개체의 이름입니다.  
  
### <a name="remarks"></a>주의  
 만드는 동안 알 수 없는 외부의 값이 확인 됩니다. 있으면 **NULL**, **IUnknown** 집계 개체에 대 한 구현 됩니다. 알 수 없는 외부 없으면 **NULL**, **IUnknown** 집계 개체에 대해 구현 됩니다.  
  
 사용 `DECLARE_POLY_AGGREGATABLE` 모두 가진 벗어날 `CComAggObject` 및 `CComObject` 집계 및 집계 되지 않은 원시 사례를 처리 하 여 모듈에 있습니다. 단일 `CComPolyObject` 개체에는 두 경우 모두 처리 합니다. 이 모듈에 vtable의 복사본이 한 개만 및 함수의 사본 하나 있는 것을 의미 합니다. Vtable 큰 경우 모듈 크기가 상당히 줄어들 수 있습니다이 있습니다. 그러나 vtable이 작은 경우를 사용 하 여 `CComPolyObject` 집계 되거나 집계 개체에 대해 최적화 되어 있지 않으므로 약간 더 큰 모듈 크기 될 수는 `CComAggObject` 및 `CComObject`.  
  
 `DECLARE_POLY_AGGREGATABLE` 매크로 ATL 컨트롤 마법사를 사용 하 여 전체 컨트롤을 만드는 경우 자동으로 개체에 선언 됩니다.  
  
##  <a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT  

 개체를 삭제 하는 경우 보호 (중 [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) 내부 집계 개체 참조 횟수 후 감소는 횟수를 증가 시킵니다 0입니다.  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="declare_view_status"></a>DECLARE_VIEW_STATUS  
 이 매크로 지정 하려면 ATL ActiveX 컨트롤의 컨트롤 클래스에 배치는 **상태 보기** 컨테이너에 대 한 플래그입니다.  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>매개 변수  
 `statusFlags`  
 [in] **VIEWSTATUS** 플래그입니다. 참조 [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) 플래그 목록은 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&126;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)

