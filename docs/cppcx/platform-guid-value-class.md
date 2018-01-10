---
title: "Platform:: guid 값 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Guid
dev_langs: C++
helpviewer_keywords: Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e65f4d046f35656cb91374c085ef2a6e4a507302
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="platformguid-value-class"></a>Platform::Guid 값 클래스
Windows 런타임 형식 시스템의 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) 형식을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
public value struct Guid  
```  
  
### <a name="members"></a>멤버  
 Guid에는 [Platform::Object Class](../cppcx/platform-object-class.md) [Platform::Type Class](../cppcx/platform-type-class.md). Guid에는 다음과 같은 멤버도 있습니다.  
  
|멤버|설명|  
|------------|-----------------|  
|[Guid](#ctor)|Guid 구조체의 새 인스턴스를 초기화합니다.|  
|[연산자==](#operator-equality)|Equals 연산자입니다.|  
|[operator!=](#operator-not-equal)|Not equals 연산자입니다.|  
|[operator()](#operator-call)|Guid를 GUID로 변환합니다.|  
  
### <a name="remarks"></a>설명  
 Windows 함수 [CoCreateGuid](http://msdn.microsoft.com/library/windows/desktop/ms688568\(v=vs.85\).aspx)를 사용하여 새 Platform::Guid를 생성하는 방법에 대한 예제는 [WinRT 구성 요소: GUID를 생성하는 방법](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)을 참조하세요.  
  
### <a name="requirements"></a>요구 사항  
 **지원 되는 최소 클라이언트:** Windows 8  
  
 **지원 되는 최소 서버:** Windows Server 2012  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  

 
## <a name="ctor"></a>Guid:: guid 생성자
Guid 구조체의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  );  
  
    Guid(GUID m);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n );  
```  
  
### <a name="parameters"></a>매개 변수  
 `a`  
 GUID의 처음 4바이트입니다.  
  
 `b`  
 GUID의 다음 2바이트입니다.  
  
 `c`  
 GUID의 다음 2바이트입니다.  
  
 `d`  
 GUID의 다음 바이트입니다.  
  
 `e`  
 GUID의 다음 바이트입니다.  
  
 `f`  
 GUID의 다음 바이트입니다.  
  
 `g`  
 GUID의 다음 바이트입니다.  
  
 `h`  
 GUID의 다음 바이트입니다.  
  
 `i`  
 GUID의 다음 바이트입니다.  
  
 `j`  
 GUID의 다음 바이트입니다.  
  
 `k`  
 GUID의 다음 바이트입니다.  
  
 `m`  
 .으로 정의된 GUID입니다.  
  
 `n`  
 GUID의 나머지 8바이트입니다.  
  

## <a name="operator-equality"></a>Guid::operator = = 연산자
두 guid를 비교합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
Platform::Guid::operator==  
```  
  
### <a name="return-value"></a>반환 값  
 두 guid가 같으면 true입니다.

## <a name="operator-inequality"></a>Guid::operator! = 연산자
두 guid를 비교합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
Platform::Guid::operator!=  
```  
  
### <a name="return-value"></a>반환 값  
 두 guid 같지 않으면 true입니다.



## <a name="operator-call"></a>Guid::operator() 연산자
암시적으로 변환 된 [GUID 구조체](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx)GUID를 platform:: guid 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
Platform::Guid operator()  
```  
  
### <a name="return-value"></a>반환 값  
 Guid 구조체입니다.  
  
  
## <a name="see-also"></a>참고 항목  
 [Platform 네임 스페이스](../cppcx/platform-namespace-c-cx.md)