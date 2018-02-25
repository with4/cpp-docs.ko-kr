---
title: "Concurrency:: graphics 네임 스페이스 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- amp_graphics/Concurrency::fast_math::copy_async
- amp_graphics/Concurrency::fast_math::copy
dev_langs:
- C++
ms.assetid: ace01cd5-29d3-4356-930e-c81a61c5f934
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d360a322cdc4ae82ebded5a441152a075e8a5fc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="concurrencygraphics-namespace-functions"></a>Concurrency:: graphics 네임 스페이스 함수
|||  
|-|-|  
|[copy](#copy)|[copy_async](#copy_async)|  
  
##  <a name="copy"></a>  copy 함수 (concurrency:: graphics Namespace)  
 원본 질감을 대상 버퍼에 복사 하거나 소스 버퍼를 대상 버퍼에 복사 합니다. 이 함수는 일반적인 형태의 `copy(src, dest)`합니다.  
  
```  
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type>  
>  
void copy (
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size,  
    _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>void copy(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture,  
    void>::type 
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Copy_extent`  
 복사할 질감 섹션의 범위입니다.  
  
 `_Dst`  
 복사할 대상 개체입니다.  
  
 `_Dst_byte_size`  
 대상의 바이트 수입니다.  
  
 `_Dst_type`  
 대상 개체의 형식입니다.  
  
 `_Dst_offset`  
 복사를 시작 하는 대상에 대 한 오프셋입니다.  
  
 `InputIterator`  
 입력된 interator의 형식입니다.  
  
 `OutputIterator`  
 출력 반복기의 형식입니다.  
  
 `_Src`  
 복사할 개체입니다.  
  
 `_Src_byte_size`  
 원본의 바이트의 수입니다.  
  
 `_Src_type`  
 원본 개체의 형식입니다.  
  
 `_Src_offset`  
 복사를 시작 하는 소스에 대 한 오프셋입니다.  
  
 `first`  
 소스 컨테이너에는 시작 반복기입니다.  
  
 `last`  
 소스 컨테이너에 사용 되는 끝 반복기입니다.  
  
##  <a name="copy_async"></a>  copy_async 함수 (concurrency:: graphics Namespace)  
 대상 버퍼에 원본 질감을 비동기적으로 복사 또는 소스 버퍼를 대상 버퍼에 복사한 다음 반환을 [completion_future](completion-future-class.md) 대기한 수 있는 개체입니다. 코드 가속기에서 실행 되는 데이터를 복사할 수 없습니다. 이 함수는 일반적인 형태의 `copy(src, dest)`합니다.  
  
```  
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type &_Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Copy_extent`  
 복사할 질감 섹션의 범위입니다.  
  
 `_Dst`  
 복사할 대상 개체입니다.  
  
 `_Dst_byte_size`  
 대상의 바이트 수입니다.  
  
 `_Dst_type`  
 대상 개체의 형식입니다.  
  
 `_Dst_offset`  
 복사를 시작 하는 대상에 대 한 오프셋입니다.  
  
 `InputIterator`  
 입력된 interator의 형식입니다.  
  
 `OutputIterator`  
 출력 반복기의 형식입니다.  
  
 `_Src`  
 복사할 개체입니다.  
  
 `_Src_byte_size`  
 원본의 바이트의 수입니다.  
  
 `_Src_type`  
 원본 개체의 형식입니다.  
  
 `_Src_offset`  
 복사를 시작 하는 소스에 대 한 오프셋입니다.  
  
 `first`  
 소스 컨테이너에는 시작 반복기입니다.  
  
 `last`  
 소스 컨테이너에 사용 되는 끝 반복기입니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** amp_graphics.h  
  
 **Namespace:** concurrency:: graphics 

## <a name="see-also"></a>참고 항목  
 [Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)
