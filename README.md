# Pico-8 Gryphon-3D-Engine-Library Conversion Tool

Please see http://www.lexaloffle.com/bbs/?tid=28077 for the pico-8 Gryphon 3D Engine.

This is a repository for the .obj to string tool for import into your pico-8 file. Detailed instructions with pictures are stored in the .pdf file (note you can toggle export of color in Blender now). This converts to a format which supports colored faces, and can be used in Gryphon 3D engine by loading them with this loading function instead of read_face().

```lua
function read_colored_face()
	f={}
	--verts 1 to 3 + 2 color values
	for i=1,5 do
		text=sub(cur_string,cur_string_index,cur_string_index+2)
		value=read_byte(text)
		--print(value)
		f[i]=value
		cur_string_index+=2
	end
	return f
end	
```
