---
title: "Module::ReleaseNotifier::ReleaseNotifier 생성자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier, constructor
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81d4f136fc9982b7260ce08d3fca4e9037f60c22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="modulereleasenotifierreleasenotifier-constructor"></a>Module::ReleaseNotifier::ReleaseNotifier 생성자
Module::ReleaseNotifier 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
ReleaseNotifier(bool release) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `release`  
 `true`Release 메서드를 호출할 때는이 인스턴스를 삭제 하려면 `false` 이 인스턴스를 삭제 하지 않도록 합니다.  
  
## <a name="exceptions"></a>예외  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Module::ReleaseNotifier 클래스](../windows/module-releasenotifier-class.md)