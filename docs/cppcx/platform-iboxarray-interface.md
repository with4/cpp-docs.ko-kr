---
title: "Platform:: iboxarray 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs:
- C++
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f52f8c95851ec80df41fe9f0838345cf46876227
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="platformiboxarray-interface"></a>Platform::IBoxArray 인터페이스
`IBoxArray` 는 XAML 컨트롤의 요소와 같은 `Platform::Object^` 요소의 컬렉션에 저장되거나 ABI(응용 프로그램 이진 인터페이스)를 통해 전달되는 값 형식의 배열에 대한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 각 배열 요소의 boxed 값 형식입니다.  
  
### <a name="remarks"></a>설명  
 `IBoxArray` C + + /cli에 대 한 CX 이름을 `Windows::Foundation::IReferenceArray`합니다.  
  
### <a name="members"></a>멤버  
 `IBoxArray` 인터페이스는 `IValueType` 인터페이스에서 상속됩니다. `IBoxArray` 에도 다음과 같은 멤버가 포함됩니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[값](#value)|이 `IBoxArray` 인스턴스에 이전에 저장된 unboxed 배열을 반환합니다.|  

## <a name="value"></a> Iboxarray:: Value 속성
이 개체에 원래 저장된 값을 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 boxed 값의 형식입니다.  
  
### <a name="property-valuereturn-value"></a>속성 값/반환 값  
 이 개체에 원래 저장된 값을 반환합니다.  
  
### <a name="remarks"></a>설명  
 예를 들어 참조 [Boxing](../cppcx/boxing-c-cx.md)합니다.  
  
  
## <a name="see-also"></a>참고 항목  
 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)