Phương thức Object.assign() trong JavaScript được sử dụng để sao chép giá trị từ một hoặc nhiều đối tượng nguồn (source objects)  
vào một đối tượng đích (target object). Nó trả về đối tượng đích sau khi đã được cập nhật với các thuộc tính và giá trị từ các đối tượng nguồn.  

Cú pháp của Object.assign() như sau:
```js
Object.assign(target, ...sources)
```
- target: Đối tượng đích, là nơi mà các thuộc tính từ các đối tượng nguồn sẽ được sao chép vào. Đối tượng này sẽ được trả về sau khi sao chép.
- sources: Một hoặc nhiều đối tượng nguồn, chứa các thuộc tính sẽ được sao chép vào đối tượng đích.

## Các bước hoạt động của Object.assign() như sau:

1. Các đối tượng nguồn được sao chép theo thứ tự từ trái sang phải. Các thuộc tính của đối tượng nguồn đầu tiên được sao chép vào đối tượng đích, sau đó đến đối tượng nguồn tiếp theo và tiếp tục cho đến hết các đối tượng nguồn.
2. Mỗi thuộc tính trong các đối tượng nguồn được sao chép vào đối tượng đích nếu nó chưa tồn tại trong đối tượng đích hoặc được ghi đè nếu đã tồn tại.
3. Phương thức Object.assign() chỉ sao chép các thuộc tính trực tiếp (own properties) của đối tượng nguồn, không sao chép các thuộc tính từ prototype chain.
4. Sau khi sao chép hoàn tất, phương thức trả về đối tượng đích đã được cập nhật.
