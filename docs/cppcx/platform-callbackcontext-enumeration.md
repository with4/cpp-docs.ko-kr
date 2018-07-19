---
title: 'Platform:: callbackcontext 열거형 | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 757de5f686bb809a5d2fb159a3ee547a20edc982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33086953"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext 열거형
콜백 함수(이벤트 처리기)가 실행되는 스레드 컨텍스트를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>멤버  
  
|형식 코드|설명|  
|---------------|-----------------|  
|임의의 값|콜백 함수가 모든 스레드 컨텍스트에서 실행될 수 있습니다.|  
|왼쪽과 같음|콜백 함수가 비동기 작업을 시작한 스레드 컨텍스트에서만 실행될 수 있습니다.|  
  
### <a name="requirements"></a>요구 사항  
 **지원 되는 최소 클라이언트:** Windows 8  
  
 **지원 되는 최소 서버:** Windows Server 2012  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd