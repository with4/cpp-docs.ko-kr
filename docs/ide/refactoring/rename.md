---
title: "이름 바꾸기 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d8e4152a1c920a243be9d4aa23712420893e29f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="rename"></a>이름 바꾸기
**:** 필드, 지역 변수, 메서드, 네임 스페이스, 속성 및 형식 등의 코드 기호에 대 한 식별자의 이름을 바꿀 수 있습니다.

**경우:** 안전 하 게 모든 인스턴스 및 새 이름 복사/붙여넣기를 필요 없이 이름을 바꿀 하는 것입니다.  

**이유:** 복사 및 프로젝트 전체에 대해 새 이름을 붙여 넣는 것 오류가 발생 합니다.  이 리팩터링 도구 이름 바꾸기 작업을 수행할 정확 하 게 됩니다.

**방법:**

1. 강조 표시 하거나 이름을 바꿀 항목 내 텍스트 커서를 놓습니다.

   ![강조 표시 된 코드](images/rename_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl + R**, 다음 **Ctrl + R**합니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
   * **마우스**
     * 선택 **편집 > 리팩터링 > 이름 바꾸기**합니다.
     * 코드를 마우스 오른쪽 단추로 클릭 하 고 선택 **이름 바꾸기**합니다.

1. 에 **이름 바꾸기** , 팝업 창에 선택 된 항목과 클릭에 대 한 새 이름을 입력 된 **미리 보기** 단추입니다.  변경 된 **검색 범위** 을 넓히거나 이름 바꾸기의 범위를 좁히려면 필요 합니다.

   ![대화 이름 바꾸기](images/rename_dialog.png)

   > [!TIP]
   > 선택 하 여 미리 보기를 건너뛸 수 있습니다는 **참조가 모두 확인 된 경우 변경 하는 미리 보기 건너뛰기** 옵션입니다.

1. 경우는 **변경 내용 미리 보기-이름 바꾸기** 창이 나타나면 변경 되 고 요청은 적절 하 게 수행 되 고 있는지 확인 합니다.  창의 상단에 모든 항목의 이름 바꾸기를 사용 하지 않도록 설정 하거나 설정 하려면 확인란을 사용 합니다.

   ![미리 보기 이름 바꾸기](images/rename_preview.png)

1. 클릭는 **적용** 단추와 해당 항목 소스 코드에서 이름이 변경 됩니다.
