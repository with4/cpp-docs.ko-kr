---
title: "보관을 통해 Cobject 저장 및 로드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 987f754ccdf03e5a252feae693a1f7718da1b353
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>보관을 통해 CObject 저장 및 로드
저장 및 로드 `CObject`보관 저장소를 통해 추가로 고려해 야 합니다. 특정 한 경우에 호출 해야는 `Serialize` 함수 개체의 위치는 `CArchive` 개체의 매개 변수는는 `Serialize` 사용 하지 않고 호출의  **< \<**  또는  **>>**  의 연산자는 `CArchive`합니다. 중요 한 사실을 염두에 `CArchive`  **>>**  연산자 구문은 `CObject` 기반으로 하는 메모리에 `CRuntimeClass` 정보 저장 보관 저장소가가 파일에 이전에 작성 합니다.  
  
 따라서 사용할지는 `CArchive`  **< \<**  및  **>>**  호출 비교 연산자 `Serialize`, 여부에 따라 달라 집니다 있습니다 *필요* 를 동적으로 개체를 다시 생성 기록을 로드에 따라 이전에 저장 된 `CRuntimeClass` 정보입니다. 사용 하 여 `Serialize` 다음과 같은 경우에는 함수:  
  
-   개체를 역직렬화 할 때 개체의 정확한 클래스 미리 알고 있습니다.  
  
-   개체를 역직렬화 할 때 할당 된 메모리를 이미 있습니다.  
  
> [!CAUTION]
>  사용 하 여 개체를 로드 하는 경우는 `Serialize` 함수를 사용 하 여 개체 저장 해야는 `Serialize` 함수입니다. 사용 하 여 저장 하지 않습니다는 `CArchive`  **<<**  연산자와 사용 하 여 다음 부하는 `Serialize` 함수를 사용 하 여 저장 하거나는 `Serialize` 함수를 사용 하 여 다음 로드 **CArchive >>**연산자입니다.  
  
 다음 예제에서는 사례를 보여 줍니다.  
  
 [!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]  
  
 [!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]  
  
 요약 하자면, serializable 클래스 정의 포함 된 경우 **CObjec**해야 멤버로 t, *하지* 사용는 `CArchive`  **< \<**  및  **>>**  해당 개체에 대 한 연산자를 호출 해야 하지만 `Serialize` 함수를 대신 합니다. 또한 serializable 클래스에 대 한 포인터를 정의 하는 경우는 `CObject` (에서 파생 된 개체 또는 `CObject`) 회원 같지만 구문 자체 생성자에서이 다른 개체도 호출 해야 `Serialize`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)

