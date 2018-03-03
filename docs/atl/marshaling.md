---
title: "마샬링 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f89b64794c50e381c07749984ce61579951fa02f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="marshaling"></a>마샬링
COM 기술은 마샬링 한 프로세스가 다른 프로세스에서 사용할 수의 개체에 의해 노출 되는 인터페이스 수 있습니다. 마샬링과 마찬가지로 COM 코드를 제공 (또는 인터페이스 구현 자가에서 제공 하는 코드를 사용 하 여)를 메서드의 매개 변수 프로세스 간에 (뿐만 아니라, 다른 컴퓨터에서 실행 중인 프로세스를 통해) 이동할 수 있는 형식으로 압축 하 고 압축을 푸는 이러한 매개 변수 다른 쪽 끝입니다. 마찬가지로, COM 호출에서 반환 된 값에도 이와 동일한 단계를 수행 해야 합니다.  
  
> [!NOTE]
>  마샬링 일반적으로 필요 하지 않으므로 개체와 동일한 프로세스에서 개체에 의해 제공 되는 인터페이스를 사용 하는 경우 그러나 마샬링 스레드 간 필요할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [마샬링 정보](http://msdn.microsoft.com/library/windows/desktop/ms692621)

