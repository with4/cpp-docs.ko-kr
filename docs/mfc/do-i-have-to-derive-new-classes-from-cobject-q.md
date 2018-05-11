---
title: CObject에서 새 클래스를 파생시켜야 합니까? | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51904ac06ae6c2db5586f8dc405f85145c5b1f30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject에서 새 클래스를 파생시켜야 합니까?
아니요, 수행하지 않습니다.  
  
 클래스를 파생 [CObject](../mfc/reference/cobject-class.md) serialization 또는 동적 creatability 같은 제공 해야 합니다. 많은 데이터 클래스는 파일에 대해 serialize되어야 하므로 `CObject`에서 해당 클래스를 파생하는 것이 좋습니다. 파생 된 클래스의 예 `CObject`, 참조는 [Scribble 샘플](../visual-cpp-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스: 질문과 대답](../mfc/cobject-class-frequently-asked-questions.md)
