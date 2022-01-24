---
layout: default
---

Here is an example of a mip map chain:

179

​

180

​

181

This happens automatically by the game engine, you don't have to do anything.

182

​

183

**So how does this relate to power of 2?**

184

Now here is the thing. If you don't use a power of 2 texture, your texture can get corrupted by compression and it is visible at longer distances or when you look at the mesh from an angle. The texture will still work and you will see it on your model, but there are issues behind it.

185

​

186

Another thing is, in some game engines, for example Unreal Engine, mip mapping doesn't even occur if you don't use a power of 2 texture. Unity engine (the one **Cities Skylines** uses) has a different workaround. 

187

​

188

The engine let's you use non-power of two textures, but those take **more memory and are slower to read by the GPU**, because the engine forces mip maps, and to do that it scales and pads your texture to the next power of 2, so for performance reasons **always stick to power of 2** on your texture resolution.

189

​

190

### 9) Texture size

191

​

192

At the end of the guide, let’s discuss texture sizes, as this is again, a performance hog like all the others. The larger the image resolution size, the more memory (VRAM in your GPU) it will use when trying to render it on the screen.

193

​

194

**Let me first explain to you a few things:**

195

Whenever you save the textures that you do as PNG on your hard drive, that size in kilobytes or megabytes doesn’t matter, as the textures will get compressed through DXT when imported ingame, DXT being a compression format.

196

​

197

Also a thing to point out is that the memory usage is not dependent on how complex or detailed the texture is.

198

​

199

**The only thing that matters is the resolution size so you should strive to make this as low as possible while keeping some nice detail.**

200

​

201

As explained in the previous chapter, in **Cities Skylines**, DXT will compress the textures for efficient storage in the following way:

202

_diffuse

203

_alpha + _color + _illumination together (ACI)

204

_normal + _specular together (XYS)

205

​

206

You can see a good chart made by **Ronyx69** to see what size those compressed textures will have:

207

​

208

_above chart is in MB_

209

​

210

Keep in mind that the final size on the asset is not 100% from textures alone, but those are usually most of it.

211

​

212

**OK, so what now?**

213

Well, if it's not obvious by now, the same as with triangles count: don't use a texture size larger than needed. Easy right? This is the biggest problem, because to do this properly you need some experience. When I first started making assets, I was absolute garbage, and I made some horrible mistakes, going with huge sizes for textures which nowadays I could make them in half the size or lower.

214

​

215

The problem comes in the way people got used to making assets and lack of experience in the right 'direction', and this is where people will start hating me, but it is the reality. A lot of asset creators simply find a good photo of the building (or parts of it) they want to make, import it in blender, and then extrude faces on those. And then they teach other creators how to do this and the cycle keeps repeating in a bad way. 

216

​

217

But what’s wrong with that you might ask. The problem with this is you end up with quite a big resolution size for the textures, because they prefer to have larger faces which cover a big size on the texture instead of trying to think what parts of the texture could be reused, what areas could be tiled, and so on which in turn would make the resolution size way smaller, but that is a topic for another day, or a different guide. Here I just want to focus on things which affect the performance.

218

​

219

I can safely say that the vast majority of assets don't need a texture higher than 2048 resolution, and also not everything needs to be modeled out.

220

​

221

### Outro

222

​

223

This is the end of the guide and I truly hope you take those tips and tricks in your arsenal when you do assets for Cities Skylines.

224

​

225

Initially I was trying to think of an order of importance in terms of performance but thinking about it, all those are pretty much equally important, and **shouldn’t be ignored.**

226

​

227

**For example:**

228

A mesh with no textures but high amount of triangles = triangle count is the problem

229

A 100 tris mesh with 4k resolution size texture = texture size is the problem

230

A low tris mesh with low resolution but with overlapping faces everywhere = overdraw is the issue

231

… and so on

232

​

233

In the end, read this guide, refer back to it and think about all those things when you create your next asset. Try to constantly make progress and each new asset that you do, should be better than the previous one, as you keep on learning and you can see the mistakes that you made in the past.

234

​

235

Hope this was useful to you, and if it was, share it with others.

236

**Comrade Intense**, peace.
