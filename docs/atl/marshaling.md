---
title: 마샬링 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2b8b82d5369aa536dab638efa379089325d10b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="marshaling"></a>마샬링
COM 기술은 마샬링 한 프로세스가 다른 프로세스에서 사용할 수의 개체에 의해 노출 되는 인터페이스 수 있습니다. 마샬링과 마찬가지로 COM 코드를 제공 (또는 인터페이스 구현 자가에서 제공 하는 코드를 사용 하 여)를 메서드의 매개 변수 프로세스 간에 (뿐만 아니라, 다른 컴퓨터에서 실행 중인 프로세스를 통해) 이동할 수 있는 형식으로 압축 하 고 압축을 푸는 이러한 매개 변수 다른 쪽 끝입니다. 마찬가지로, COM 호출에서 반환 된 값에도 이와 동일한 단계를 수행 해야 합니다.  
  
> [!NOTE]
>  마샬링 일반적으로 필요 하지 않으므로 개체와 동일한 프로세스에서 개체에 의해 제공 되는 인터페이스를 사용 하는 경우 그러나 마샬링 스레드 간 필요할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [마샬링 정보](http://msdn.microsoft.com/library/windows/desktop/ms692621)

