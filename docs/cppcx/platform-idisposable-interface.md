---
title: 'Platform:: idisposable 인터페이스 | Microsoft Docs'
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
dev_langs:
- C++
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68c5425d5d65acc194287a97068df7da15f37275
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33086975"
---
# <a name="platformidisposable-interface"></a>Platform::IDisposable 인터페이스
관리되지 않는 리소스를 해제하는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
public interface class IDisposable  
```  
  
## <a name="attributes"></a>특성  
 **GuidAttribute**("de0cbaea-8065-4a45-b196-c9d443f9bab3")  
  
 **VersionAttribute**(NTDDI_WIN8)  
  
### <a name="members"></a>멤버  
 IDisposable 인터페이스는 IUnknown 인터페이스에서 상속됩니다. IDisposable에는 다음 형식의 멤버도 있습니다.  
  
 **메서드**  
  
 IDisposable 인터페이스에는 다음 메서드가 있습니다.  
  
|메서드|설명|  
|------------|-----------------|  
|Dispose|관리되지 않는 리소스를 해제하는 데 사용됩니다.|  
  
### <a name="requirements"></a>요구 사항  
 **지원 되는 최소 클라이언트:** Windows 8  
  
 **지원 되는 최소 서버:** Windows Server 2012  
  
 **네임스페이스:** Platform