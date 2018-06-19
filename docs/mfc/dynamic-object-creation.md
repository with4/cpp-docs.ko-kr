---
title: 동적 개체 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5763e3f0f3ee5a0e58ac20fe9f637e4f7e097999
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346648"
---
# <a name="dynamic-object-creation"></a>동적 개체 만들기
이 문서를 런타임에 동적으로 개체를 만드는 방법을 설명 합니다. 프로시저는 문서에 설명 된 대로 런타임 클래스 정보를 사용 하 여 [런타임 클래스 정보 액세스](../mfc/accessing-run-time-class-information.md)합니다.  
  
#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>동적으로 런타임 클래스를 지정 된 개체를 만들려면  
  
1.  다음 코드를 사용 하 여 동적으로 사용 하 여 개체를 만들려면는 `CreateObject` 의 함수는 `CRuntimeClass`합니다. 실패 한 경우, 유의 `CreateObject` 반환 **NULL** 예외를 발생 시키는 대신:  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CObject 사용](../mfc/using-cobject.md)

