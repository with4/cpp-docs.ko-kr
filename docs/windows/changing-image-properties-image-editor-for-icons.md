---
title: 이미지 속성 (아이콘에 대 한 이미지 편집기) 변경 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- images [C++], properties
- Image editor [C++], Properties window
- Image editor [C++], image properties
- Properties window, image editor
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 79903e198ddd418b96b0fac2a464dc130d81614e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863332"
---
# <a name="changing-image-properties-image-editor-for-icons"></a>이미지 속성 변경(아이콘에 대한 이미지 편집기)
설정 하거나 사용 하 여 이미지의 속성을 수정할 수는 [속성 창](/visualstudio/ide/reference/properties-window)합니다.  
  
### <a name="to-change-an-images-properties"></a>이미지의 속성을 변경 하려면  
  
1.  이미지에서 열고는 **이미지** 편집기입니다.  
  
2.  에 **속성** 창 이미지에 대 한 일부 또는 모든 속성을 변경 합니다.  
  
    |속성|설명|  
    |--------------|-----------------|  
    |**색**|이미지에 대 한 색 구성표를 지정합니다. 단색, 16, 또는 256, 또는 True 색을 선택 합니다. 이미지에 16 색상표를 사용 하 여 이미지 이미 모델링 다이어그램 단색을 선택 흑백 색에 대 한 대체 하면 합니다. 대비 항상 유지 되지 않습니다: 예를 들어 빨간색 및 녹색의 인접 한 영역 둘 다로 변환할지 검정.|  
    |**Filename**|이미지 파일의 이름을 지정합니다. 기본적으로 Visual Studio에서 기본 리소스 식별자 (IDB_BITMAP1) 적절 한 확장명을 추가 하는 처음 4 자리 ("IDB_")를 제거 하 여 만든 기본 파일 이름을 할당 합니다. 이 예에서 이미지에 대 한 파일 이름을 BITMAP1.bmp 것입니다. MYBITMAP1.bmp 이름을 수 없습니다.|  
    |**높이**|이미지의 높이 (픽셀)를 설정합니다. 기본값은 48입니다. 이미지 잘리거나 기존 이미지 아래에 공백이 추가 됩니다.|  
    |**ID**|리소스의 식별자를 설정합니다. 이미지에 대 한 Microsoft Visual Studio에서는 기본적으로 할당는 계열에서 사용 가능한 다음 식별자: IDB_BITMAP1, IDB_BITMAP2, 등입니다. 이름이 비슷한 아이콘 및 커서에 사용 됩니다.|  
    |**색상표**|색 속성을 변경 합니다. 색을 선택 하 고 표시를 두 번 클릭은 [사용자 지정 색 선택 대화 상자](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)합니다. 적절 한 텍스트 상자에 RGB 또는 HSL 값을 입력 하 여 색을 정의 합니다.|  
    |**SaveCompressed**|이미지 압축 된 형식 인지 여부를 나타냅니다. 이 속성은 읽기 전용입니다. Visual Studio 이미지 압축된 된 형식으로 저장할 수를 허용 하지 않는 Visual Studio에서 만든 모든 이미지의 경우이 속성을 갖게 됩니다 **False**합니다. Visual Studio에서 (다른 프로그램에서 만든) 압축 된 이미지를 열면이 속성은 됩니다 **True**합니다. Visual Studio를 사용 하 여 압축 된 이미지를 저장 하면 압축 되 고이 속성은 되돌아갑니다 **False**합니다.|  
    |**너비**|이미지의 너비 (픽셀)를 설정합니다. 비트맵에 대 한 기본값은 48입니다. 이미지 잘리거나 기존 이미지의 오른쪽에 공백이 추가 됩니다.|  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)

