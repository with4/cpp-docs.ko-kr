---
title: "&lt;allocators&gt; macros | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cb5ee07-1ff9-4594-ae32-3c8c6efb511a
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: da17f9af1f14df13eb3871ef9ccf785356e02de4
ms.openlocfilehash: abc1dd29ba68540a6669f7aff1bbd3dffdab616a
ms.lasthandoff: 02/24/2017

---
# <a name="ltallocatorsgt-macros"></a>&lt;allocators&gt; macros
||||  
|-|-|-|  
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|  
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|  
  
##  <a name="a-nameallocatordecla--allocatordecl"></a><a name="allocator_decl"></a>  ALLOCATOR_DECL  
 할당자 템플릿 클래스를 생성합니다.  
  
```
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```  
  
### <a name="remarks"></a>설명  
 이 매크로는 동기화 필터 `sync` 및 `cache` 형식의 캐시를 사용하는 할당자 템플릿 클래스를 함께 정의하는 템플릿 정의 `template <class Type> class name {.....}` 및 특수화 `template <> class name<void> {.....}`를 생성합니다.  
  
 rebind를 컴파일할 수 있는 컴파일러의 경우, 결과 템플릿 정의는 다음과 같습니다.  
```  
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };  
 ```  
 rebind를 컴파일할 수 없는 컴파일러의 경우, 결과 템플릿 정의는 다음과 같습니다.  
  
```
template <class Type<class name
    : public stdext::allocators::allocator_base<Type,
    sync<stdext::allocators::rts_alloc<cache>>>
{
public:
    name() {}
    template <class Other>
    name(const name<Other>&) {}
    template <class Other>
    name& operator= (const name<Other>&)
    {
        return *this;
    }
};
```  
  
##  <a name="a-namecachechunklista--cachechunklist"></a><a name="cache_chunklist"></a>  CACHE_CHUNKLIST  
 `stdext::allocators::cache_chunklist<sizeof(Type)>`을 생성합니다.  
  
```
#define CACHE_CHUNKLIST <cache_class>
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="a-namecachefreelista--cachefreelist"></a><a name="cache_freelist"></a>  CACHE_FREELIST  
 `stdext::allocators::cache_freelist<sizeof(Type), max>`를 생성합니다.  
  
```
#define CACHE_FREELIST(max) <cache_class>
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="a-namecachesuballoca--cachesuballoc"></a><a name="cache_suballoc"></a>  CACHE_SUBALLOC  
 `stdext::allocators::cache_suballoc<sizeof(Type)>`을 생성합니다.  
  
```
#define CACHE_SUBALLOC <cache_class>
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="a-namesyncdefaulta--syncdefault"></a><a name="sync_default"></a>  SYNC_DEFAULT  
 동기화 필터를 생성합니다.  
  
```
#define SYNC_DEFAULT <sync_template>
```  
  
### <a name="remarks"></a>설명  
 컴파일러가 단일 스레드 및 다중 스레드 응용 프로그램 컴파일을 모두 지원하는 경우 단일 스레드 응용 프로그램에 대해 매크로는 `stdext::allocators::sync_none`을 생성하고, 다른 모든 경우 `stdext::allocators::sync_shared`를 생성합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)





