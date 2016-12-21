---
title: "__vmx_vmread | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMREAD 명령"
  - "__vmx_vmread 내장 함수"
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 현재 가상 컴퓨터 제어 구조 \(VMCS\)에서 지정 된 필드를 읽고 하 고 지정한 위치에 옮깁니다.  
  
## 구문  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|\[in\] `Field`|읽을 수 있는 VMCS 필드입니다.|  
|\[in\] `FieldValue`|VMCS 필드에서 지정한 값을 저장 하는 위치에 대 한 포인터를 읽을 `Field` 매개 변수.|  
  
## 반환 값  
  
|값|의미|  
|-------|--------|  
|0|작업이 성공 했습니다.|  
|1|작업 실패와 확장 된 상태에서 사용할 수 있는 `VM-instruction error field` 현재 VMCS의.|  
|2|사용 가능한 상태가 없으면 작업이 실패 했습니다.|  
  
## 설명  
 `__vmx_vmread` 함수는 해당 하는 `VMREAD` 컴퓨터 명령.  값은 `Field` 매개 변수는 인텔 문서에 설명 되어 있는 인코딩된 필드 인덱스입니다.  검색 문서, "인텔 가상화 기술 사양에는 ia\-32 인텔 아키텍처"에 대 한 자세한 내용은 번호 C97063\-002에서를 문서는 [인텔사](http://go.microsoft.com/fwlink/?LinkId=127) 사이트, 다음 해당 문서의 부록 C를 참조 하십시오.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__vmx_vmread`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmwrite](../intrinsics/vmx-vmwrite.md)