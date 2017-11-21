---
title: "배열, 목록 및 맵 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.mfc
dev_langs: C++
helpviewer_keywords:
- arrays [MFC], classes
- list classes [MFC]
- collection classes [MFC], maps
- map classes [MFC]
- collection classes [MFC], lists
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ff37c762049121750a342eac1cf7f310b2fbce63
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="array-list-and-map-classes"></a>배열, 목록 및 맵 클래스
클래스 라이브러리를 데이터의 집계를 처리 하기 위한 컬렉션 클래스의 그룹을 통해-목록, 배열 및 맵-다양 한 개체 및 미리 정의 된 형식을 포함 될 수 있는 합니다. 컬렉션 동적으로 크기가 조정 됩니다. 또는 Windows 용으로 작성 하는지 여부를 이러한 클래스를 모든 프로그램에서 사용할 수 있습니다. 그러나 이들 프로토콜은 응용 프로그램 프레임 워크에서 문서 클래스를 정의 하는 데이터 구조를 구현 하는 데 가장 유용 합니다. 이러한 경우에서 특수 한 컬렉션 클래스를 파생 시키고 쉽게 또는 템플릿 클래스에 따라 만들 수 있습니다. 이러한 방법에 대 한 자세한 내용은 문서 참조 [컬렉션](../mfc/collections.md)합니다. 목록이 템플릿 컬렉션 클래스에 대 한 문서를 참조 [배열, 목록 및 맵에 대 한 템플릿 클래스](../mfc/template-classes-for-arrays-lists-and-maps.md)합니다.  
  
 배열은 1 차원 데이터 구조를 연속적으로 메모리에 저장 됩니다. 요소의 인덱스에 요소 크기를 곱한 기본 주소 배열에 결과 추가 하 여 지정 된 요소의 메모리 주소를 계산할 수 있으므로 매우 빠른 임의 액세스를 지원 합니다. 하지만 배열은 부담이 삽입할 요소에 대 한 공간을 만들기 위해 이동 해야 하는 요소를 삽입 이후 지난 전체 배열 요소를 배열에 삽입할 해야 할 경우. 배열 증가 하 고 필요에 따라 축소할 수 있습니다.  
  
 목록은 배열 유사 하지만 매우 다르게 저장 됩니다. 목록에서 각 요소에는 이중 연결된 목록이 있으므로 이전 및 다음 요소에 대 한 포인터도 포함 됩니다. 추가 항목을 하거나 삭제할 것만 이렇게 몇 가지 지침을 변경 하기 때문에 매우 빠릅니다. 그러나 목록을 검색 비쌉니다 모든 검색에는 목록 끝 중 하나에서 시작 필요가 없기 때문입니다.  
  
 지도는 데이터 값에는 키 값을 연결합니다. 예를 들어, 문자열 및 데이터에 대 한 포인터 목록으로 지도 키 수 있습니다. 관련 된 특정 문자열 포인터를 제공 하는 지도 요청 합니다. 맵 조회는 키 조회에 해시 테이블을 사용 하는 지도 빠릅니다. 항목 추가 및 삭제 빠른 이기도 합니다. 지도 보조 인덱스와 기타 데이터 구조에 자주 사용 됩니다. MFC는 특수 한 유형의 지도 호출을 사용 하 여는 [메시지 맵을](../mfc/mapping-messages.md) Windows 메시지를 해당 메시지 처리기 함수에 대 한 포인터를 매핑할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

