---
title: IUnknown | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IUnknown
dev_langs: C++
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f750cea17029a76f56edaa3dc6531554fa81901a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="iunknown"></a>IUnknown
[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 는 다른 모든 COM 인터페이스의 기본 인터페이스입니다.  이 인터페이스는 세 가지 방법 정의: [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), 및 [릴리스](http://msdn.microsoft.com/library/windows/desktop/ms682317)합니다. [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) 다른 인터페이스 포인터에 대 한 개체를 요청 하는 인터페이스 사용자 수 있습니다. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) 및 [릴리스](http://msdn.microsoft.com/library/windows/desktop/ms682317) 인터페이스의 참조 횟수를 구현 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [IUnknown 및 인터페이스 상속](http://msdn.microsoft.com/library/windows/desktop/ms692713)

