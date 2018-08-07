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
ms.openlocfilehash: 8e0ce8b2cc412c576b0eded9662d8e70b34cf2ec
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850815"
---
# <a name="reference-counting"></a>참조 계산
자체 COM 개체는 더 이상 사용 되지 않는 것이 생각 하는 경우 메모리에서 개체를 제거 하려면 자동으로 시도 하지 않습니다. 대신 개체 프로그래머는 사용 되지 않는 개체를 제거 해야 합니다. 프로그래머가 여부는 개체를 제거할 수 참조 횟수에 따라 결정 합니다.  
  
 COM 사용 합니다 `IUnknown` 메서드를 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) 및 [릴리스](http://msdn.microsoft.com/library/windows/desktop/ms682317), 개체에 대 한 인터페이스의 참조 횟수를 관리 합니다. 이러한 메서드를 호출 하는 것에 대 한 일반 규칙은:  
  
-   클라이언트 인터페이스 포인터를 수신할 때마다 `AddRef` 인터페이스에서 호출 해야 합니다.  
  
-   클라이언트 인터페이스 포인터를 사용 하 여 완료 되 면 때마다 호출 해야 `Release`합니다.  
  
 간단한 구현에서 각 `AddRef` 증가 하 고 각 호출 `Release` 감소 개체 내의 카운터 변수를 호출 합니다. 개수를 0으로 반환 될 때 인터페이스를 더 이상 모든 사용자가 있으며 메모리에서 자신을 제거할 수도 없습니다.  
  
 참조 횟수를 구현할 수도 있습니다 (필요가, 개별 인터페이스) 개체에 대 한 각 참조는 계산 되도록 합니다. 이 경우 각 `AddRef` 및 `Release` 개체에 대해 중앙 구현에 대리자를 호출 하 고 `Release` 해당 참조 횟수가 0에 도달 하면 전체 개체를 해제 합니다.  
  
> [!NOTE]
>  경우는 `CComObject`-파생된 개체가 사용 하 여 생성 되는 **새** 연산자는 참조 횟수가 0입니다. 따라서 호출 `AddRef` 성공적으로 만든 후 다시 만들어야 합니다 `CComObject`-파생 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [참조 횟수를 통해 개체 수명 관리](http://msdn.microsoft.com/library/windows/desktop/ms687260)

