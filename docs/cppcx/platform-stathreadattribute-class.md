---
title: "Platform:: stathreadattribute 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
dev_langs: C++
helpviewer_keywords: Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1c2b8c38d672b6bd3ecd0fcafb54a9b6e723202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute 클래스
응용 프로그램에 대한 스레딩 모델이 STA(단일 스레드 아파트)임을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
public ref class STAThreadAttribute sealed : Attribute  
```  
  
### <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[STAThreadAttribute 생성자 1](#ctor)|클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
 STAThreadAttribute 특성에서 상속 [platform:: object 클래스](../cppcx/platform-object-class.md)합니다. STAThreadAttribute도 다음 멤버를 오버로드하거나 포함합니다.  
  
|name|설명|  
|----------|-----------------|  
|[STAThreadAttribute::Equals](#equals)|지정한 개체와 현재 개체가 같은지 여부를 확인합니다.|  
|[STAThreadAttribute::GetHashCode](#gethashcode)|이 인스턴스의 해시 코드를 반환합니다.|  
|[STAThreadAttribute::ToString](#tostring)|현재 개체를 나타내는 문자열을 반환합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Platform`  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform  



## <a name="ctor"></a> STAThreadAttribute constructor
STAThreadAttribute 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
public:STAThreadAttribute()  
```  
  


## <a name="equals"></a>STAThreadAttribute::Equals
지정한 개체와 현재 개체가 같은지 여부를 확인합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
### <a name="parameters"></a>매개 변수  
 obj  
 비교할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 개체가 동일하면 `true`이고, 그렇지 않으면 `false`입니다.  
  


## <a name="gethashcode"></a>STAThreadAttribute::GetHashCode
이 인스턴스의 해시 코드를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>반환 값  
 이 인스턴스의 해시 코드입니다.  
  


## <a name="tostring"></a>STAThreadAttribute::ToString
현재 개체를 나타내는 문자열을 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
public:String^ ToString()  
```  
  
### <a name="return-value"></a>반환 값  
 현재 개체를 나타내는 문자열입니다.  
  

  
## <a name="see-also"></a>참고 항목  
 [플랫폼 Namespace](platform-namespace-c-cx.md)