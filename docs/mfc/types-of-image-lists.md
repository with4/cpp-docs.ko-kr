---
title: 이미지 목록 형식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8988dc55bbbaa1d446ee14bf78a0cd799b422834
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385887"
---
# <a name="types-of-image-lists"></a>이미지 목록 형식
이미지 목록에 두 가지 ([CImageList](../mfc/reference/cimagelist-class.md)): 마스크 되지 않은 및 마스크입니다. "마스크 되지 않은 이미지 목록" 하나 이상의 이미지를 포함 하는 색 비트맵으로 이루어져 있습니다. "마스크 된 이미지 목록" 동일한 크기의 두 개의 비트맵으로 이루어져 있습니다. 첫 번째 색 비트맵 이미지를 포함 하 고 두 번째는 일련의 마스크를 포함 하는 단색 비트맵-각 이미지는 첫 번째 비트맵에 대해 하나씩입니다.  
  
 오버 로드 중 하나는 **만들기** 멤버 함수는 이미지 목록을 마스크 되어 있는지 여부를 표시 하는 플래그를 사용 합니다. (다른 오버 로드에는 마스크 된 이미지 목록을 만듭니다.)  
  
 대상 장치 컨텍스트로; 복사 하기만 하면 마스크 되지 않은 이미지를 그릴 때 즉, 기존 배경색 장치 컨텍스트의 위에 그려집니다. 마스크 된 이미지를 그릴 때 일반적으로 대상 장치 컨텍스트의 배경색 비쳐 비트맵의 투명 영역을 생성 하는 마스크의 비트와 이미지의 비트 결합 됩니다. 마스크 된 이미지를 그릴 때 여러 그리기 스타일을 지정할 수 있습니다. 예를 들어 이미지를 선택한 개체를 나타내는 디더링 수를 지정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)

