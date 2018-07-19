---
title: CArchive 개체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55b97843a8aeb2599d2bdf34458b362fc5899368
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383836"
---
# <a name="what-is-a-carchive-object"></a>CArchive 개체
A `CArchive` 쓰거나 간에 직렬화 가능 개체를 읽는 데 형식이 안전한 버퍼링 메커니즘을 제공 하는 개체는 `CFile` 개체입니다. 일반적으로 `CFile` 개체 디스크 파일을 나타냅니다; 그러나 파일을 메모리를 사용할 수도 있습니다 (`CSharedFile` 개체), 아마도 클립보드를 나타내는입니다.  
  
 지정 된 `CArchive` 중 저장소 개체 (기록, 직렬화) 데이터 또는 부하 (읽기, 역직렬화) 데이터를 다르다는 하지 않습니다. 수명 주기는 `CArchive` 개체는 하나 이상의 통과 개체 파일에 쓰거나 파일에서 개체를 읽는으로 제한 됩니다. 따라서 연속적으로 만든 두 `CArchive` 개체는 데이터를 파일에 serialize 한 다음 파일에서 다시 deserialize 해야 합니다.  
  
 보관 파일에 개체를 저장, 보관 파일 첨부는 `CRuntimeClass` 개체 이름입니다. 그런 다음 다른 보관 파일에서 메모리에 개체를 로드 하는 경우는 `CObject`-파생 된 개체가 동적으로 다시 구성 해야에 따라는 `CRuntimeClass` 개체입니다. 저장 보관 하 여 파일에 기록 될 때 지정된 된 개체를 두 번 이상 참조할 수 있습니다. 그러나 로드 보관는 개체를 다시 생성 한 번만 합니다. 아카이브 연결 하는 방법에 대 한 세부 정보 `CRuntimeClass` 에 설명 된 정보를 개체 및 여러 참조 수를 고려 하는 개체를 다시 만듭니다 [기술 참고 2](../mfc/tn002-persistent-object-data-format.md)합니다.  
  
 데이터 보관으로 serialize 되는, 대로 해당 버퍼가 가득 찰 때까지 보관 된 데이터를 누적 합니다. 한 다음 해당 버퍼를 보관 파일에 씁니다는 `CFile` 가리키는 개체는 `CArchive` 개체입니다. 마찬가지로, 아카이브 열에서 데이터를 읽는 데이터를 읽을 버퍼에 파일에서 한 다음 deserialize 된 개체에 대 한 버퍼에서 합니다. 이 버퍼링 되므로 응용 프로그램의 성능이 향상 하드 디스크는 읽는 물리적으로 횟수가 줄어듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)

