---
title: IUnknown | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d832d2978bf9db82b290d77b236fea1c9bcada58
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953044"
---
# <a name="iunknown"></a>IUnknown
[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 마다 다른 COM 인터페이스의 기본 인터페이스입니다.  이 인터페이스는 세 가지 메서드를 정의 합니다. [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), 및 [릴리스](http://msdn.microsoft.com/library/windows/desktop/ms682317). [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) 인터페이스 사용자가 다른 인터페이스에 대 한 포인터에 대 한 개체를 요청할 수 있습니다. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) 하 고 [릴리스](http://msdn.microsoft.com/library/windows/desktop/ms682317) 인터페이스의 참조 횟수를 구현 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [IUnknown 및 인터페이스 상속](http://msdn.microsoft.com/library/windows/desktop/ms692713)

