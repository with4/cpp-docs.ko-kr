---
title: CArchive를 사용 하 여 &lt; &lt; 및 &gt; &gt; 연산자 | Microsoft Docs
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
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82b729caaa650fde72741497d3f4ab3c131f46ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive를 사용 하 여 &lt; &lt; 및 &gt; &gt; 연산자
`CArchive` 제공 <\< 및 >> 작성 및 단순 데이터 형식을 읽기 위한 연산자와 `CObject`하 고 파일에서 s입니다.  
  
#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>보관을 통해 파일에 있는 개체를 저장 하려면  
  
1.  다음 예제에서는 보관을 통해 파일에 있는 개체를 저장 하는 방법을 보여 줍니다.  
  
     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]  
  
#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>이전에 파일에 저장 된 값에서 개체를 로드 하려면  
  
1.  다음 예제에서는 이전에 파일에 저장 된 값에서 개체를 로드 하는 방법을 보여 줍니다.  
  
     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]  
  
 저장 하 고에 보관을 통해 파일 간에 데이터를 로드 하는 일반적으로 `Serialize` 의 기능 `CObject`-있는 선언한 해야 하는 클래스를 파생 된 **DECLARE_SERIALIZE** 매크로입니다. 에 대 한 참조는 `CArchive` 를 전달 하 여 `Serialize` 함수입니다. 호출 하면는 `IsLoading` 의 함수는 `CArchive` 결정 하는 개체 여부는 `Serialize` 파일에서 데이터를 로드 하거나 파일의 데이터를 저장 기능을 호출 했습니다.  
  
 `Serialize` 함수는 직렬화 가능의 `CObject`-파생된 클래스에는 일반적으로 형식은 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]  
  
 위의 코드 서식 파일은 정확히 하나에 대 한 응용 프로그램 마법사에서는 동일는 `Serialize` 문서의 함수 (클래스에서 파생 **CDocument)** 합니다. 이 코드 서식 파일을 저장 코드와 로딩 코드는 다음 예제와 같이 병렬 항상 이어야 하기 때문에 보다 잘를 검토할 수 있는 코드를 작성할 수 있습니다.  
  
 [!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]  
  
 라이브러리 정의 **< \<** 및 **>>** 연산자에 대 한 `CArchive` 첫째 피연산자 다음 데이터 형식 및 두 번째 피연산자와 클래스 형식 :  
  
||||  
|-|-|-|  
|`CObject*`|**크기와 CSize**|**float**|  
|**WORD**|`CString`|**지점** 및 `CPoint`|  
|`DWORD`|**BYTE**|`RECT` 및 `CRect`|  
|**Double**|**LONG**|`CTime` 및 `CTimeSpan`|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  저장 및 로드 `CObject`보관 저장소를 통해 추가로 고려해 야 합니다. 자세한 내용은 참조 [를 저장 하 고 보관을 통해 Cobject 로드](../mfc/storing-and-loading-cobjects-via-an-archive.md)합니다.  
  
 **CArchive <\<**  및 **>>** 연산자에 대 한 참조를 항상 반환는 `CArchive` 개체 첫 번째 피연산자입니다. 이렇게 하면 아래 그림과 같이 연산자를 연결할 수 있습니다.  
  
 [!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)

