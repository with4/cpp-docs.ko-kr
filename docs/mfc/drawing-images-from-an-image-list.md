---
title: 이미지 목록에서 이미지 그리기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ebc05a83eb22d494a75ed474e315112522af3fc
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932070"
---
# <a name="drawing-images-from-an-image-list"></a>이미지 목록에서 이미지 그리기
이미지를 그리기 위해 사용 하 여는 [CImageList::Draw](../mfc/reference/cimagelist-class.md#draw) 멤버 함수입니다. 장치 컨텍스트 개체를 그릴 위치를 이미지를 그릴 장치 컨텍스트에서 이미지의 인덱스 및 그리기 스타일을 표시 하기 위해 플래그 집합이에 대 한 포인터를 지정 합니다.  
  
 지정 하는 경우는 **ILD_TRANSPARENT** 스타일 `Draw` 마스크 된 이미지를 그릴 2 단계 프로세스를 사용 합니다. 먼저, 논리적 수행-및 이미지의 비트와 마스크의 비트에 대 한 작업이 있습니다. 그런 다음 첫 번째 작업의 결과와 대상 장치 컨텍스트의 백그라운드 비트 논리적 XOR 연산을 수행합니다. 이 프로세스 결과 이미지; 투명 한 영역 생성 즉, 각 흰색 비트 마스크의 해당 비트 결과 이미지 투명 하 게 됩니다.  
  
 사용 해야 단색 배경에 마스크 된 이미지를 그리기를 하기 전에 [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor) 멤버 함수를 대상으로 동일한 색 이미지 목록의 배경색을 설정 합니다. 이미지에서 투명 한 영역을 만들 필요가 없습니다 색을 설정 및 사용 `Draw` 하기만 하면 상당한 성능 향상에서으로 인해 발생 하는 대상 장치 컨텍스트에 이미지를 복사 합니다. 이미지를 그릴, 지정 된 **ILD_NORMAL** 호출 하는 경우 스타일 `Draw`합니다.  
  
 마스크 된 이미지 목록에 대 한 배경색을 설정할 수 있습니다 ([CImageList](../mfc/reference/cimagelist-class.md)) 언제 든 지 하므로 한다는 모든 단색 배경에서 올바르게 그립니다. 명령 프롬프트 창의 배경색을 설정 **CLR_NONE** 이미지를 그릴 기본적으로 투명 하 게 발생 합니다. 이미지 목록의 배경색을 검색 하려면는 [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor) 멤버 함수입니다.  
  
 **ILD_BLEND25** 및 **ILD_BLEND50** 스타일 디더링 시스템 강조 색을 사용 하 여 이미지입니다. 이러한 스타일은 마스크 된 이미지를 사용 하 여 사용자가 선택할 수 있는 개체를 나타내는 경우에 유용 합니다. 예를 들어, 사용할 수는 **ILD_BLEND50** 스타일을 선택할 경우 이미지를 그립니다.  
  
 마스크 되지 않은 이미지를 사용 하 여 대상 장치 컨텍스트에에 복사 되는 `SRCCOPY` 래스터 작업 합니다. 이미지의 색상 장치 컨텍스트의 배경색에 관계 없이 동일 하 게 표시 합니다. 에 지정 된 그리기 스타일 `Draw` 레이블에도 마스크 되지 않은 이미지의 모양에 영향을 주지 않습니다.  
  
 멤버 함수 Draw, 다른 함수 외에도 [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect), 이미지를 렌더링 하는 기능을 확장 합니다. `DrawIndirect` 매개 변수로 하나는 [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) 구조입니다. 이 구조를 사용 하 여 래스터 연산 (ROP) 코드의 사용을 포함 하 여 현재 이미지 렌더링을 사용자 지정할 수 있습니다. ROP 코드에 대 한 자세한 내용은 참조 하십시오. [래스터 연산 코드](http://msdn.microsoft.com/library/windows/desktop/dd162892) 및 [브러시 비트맵](http://msdn.microsoft.com/library/windows/desktop/dd183378) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)

