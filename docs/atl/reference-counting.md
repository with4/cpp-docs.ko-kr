---
title: 참조 횟수 (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1ba27f00bf25f88575101b1299daf50f94000ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358250"
---
# <a name="reference-counting"></a>참조 횟수
자체 COM 개체가 더 이상 사용 되지 것으로 확인 하는 경우 메모리에서 개체를 제거 하려면 자동으로 시도 하지 않습니다. 대신, 개체 프로그래머가 사용 하지 않는 개체를 제거 해야 합니다. 프로그래머가 여부는 개체를 제거할 수 참조 횟수에 따라 결정 합니다.  
  
 COM 사용 하 여는 **IUnknown** 메서드 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) 및 [릴리스](http://msdn.microsoft.com/library/windows/desktop/ms682317), 개체에 대 한 인터페이스의 참조 횟수를 관리할 수 있습니다. 이러한 메서드를 호출 하기 위한 일반적인 규칙은:  
  
-   클라이언트는 인터페이스 포인터를 받을 때마다 `AddRef` 인터페이스에서 호출 되어야 합니다.  
  
-   인터페이스 포인터를 사용 하 여 클라이언트가 완료 될 때마다 호출 해야 **릴리스**합니다.  
  
 간단한 구현에서 각 `AddRef` 증가 하 고 각 호출 **릴리스** 감소 개체 내의 카운터 변수를 호출 합니다. 개수를 0으로 반환 될 때 인터페이스를 더 이상 사용자 고 메모리에서 제거 무료입니다.  
  
 참조 횟수 구현할 수도 있습니다 (되지 않도록 개체 개별 인터페이스)에 대 한 각 참조 횟수가 계산 되도록 합니다. 이 경우 각 `AddRef` 및 **릴리스** 개체에서 중앙 구현에 대리자를 호출 하 고 **릴리스** 전체 개체 참조 개수가 0에 도달할 때 실행을 해제 합니다.  
  
> [!NOTE]
>  경우는 `CComObject`-파생 된 개체가 사용 하 여 생성 되는 **새** 연산자, 참조 횟수는 0입니다. 에 대 한 호출 이므로 `AddRef` 성공적으로 만든 후 이루어져야 합니다는 `CComObject`-파생 된 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [참조 횟수를 통해 개체 수명 관리](http://msdn.microsoft.com/library/windows/desktop/ms687260)

