## Chapter 2 Representing Position and Orientation

A fundamental requirement in robotics and computer vision is to represent the position and orientation of objects in an environment. Such objects include robots, cameras, work pieces, obstacles and paths.

A point in space is a familiar concept from mathematics and can be described by a coordinate vector, also known as a bound vector, as shown in Fig. 2.1a. The vector represents the displacement of the point with respect to some reference coordinate frame. A coordinate frame, or Cartesian coordinate system, is a set of orthogonal axes which intersect at a point known as the origin.

More frequently we need to consider a set of points that comprise some object. We assume that the object is  rigid and that its constituent points maintain a constant relative position with respect to the object’s coordinate frame as shown in Fig. 2.1b. Instead of describing the individual points we describe the position and orientation of the object by the position and orientation of its coordinate frame. A coordinate frame is labelled, {B} in this case, and its axis labels x<sub>B</sub> and y<sub>B</sub> adopt the frame’s label as their subscript.

Fig. 2.1.

**a** The point P is described by a coordinate vector with respect to an absolute coordinate frame. **b** The points are described with respect to the object’s coordinate frame {B} which in turn is described by a relative pose ξ<sub>B</sub>. Axes are denoted by thick lines with an open arrow, vectors by thin lines with a swept arrow head and a pose by a thick line with a solid head

Fig. 2.2.

The point P can be described by coordinate vectors relative to either frame {A} or {B}. The pose of {B} relative to {A} is <sup>A</sup>ξ<sub>B</sub>

The position and orientation of a coordinate frame is known as its pose and is shown graphically as a set of coordinate axes. The relative pose of a frame with respect to a reference coordinate frame is denoted  by the symbol ξ – pronounced ksi. Figure 2.2 shows two frames {A} and {B} and the relative pose <sup>A</sup>ξ<sub>B</sub> which describes {B} with respect to {A}. The leading superscript denotes the reference coordinate frame and the subscript denotes the frame being described. We could also think of <sup>A</sup>ξ<sub>B</sub> as describing some motion – imagine picking up {A} and applying a displacement and a rotation so that it is transformed to {B}. If the initial superscript is missing we assume that the change in pose is relative to the world coordinate frame denoted O.

The point P in Fig. 2.2 can be described with respect to either coordinate frame.Formally we express this as

(2.1)

where the right-hand side expresses the motion from {A} to {B} and then to P. The operator · transforms the vector, resulting in a new vector that describes the same point but with respect to a different coordinate frame.


An important characteristic of relative poses is that they can be composed or compounded. Consider the case shown in Fig. 2.3. If one frame can be described in terms of another by a relative pose then they can be applied sequentially


which says, in words, that the pose of {C} relative to {A} can be obtained by compounding the relative poses from {A} to {B} and {B} to {C}. We use the operator ⊕ to indicate composition of relative poses.

For this case the point P can be described



Later in this chapter we will convert these abstract notions of ξ, · and ⊕ into standard mathematical objects and operators that we can implement in MATLAB®.

In the examples so far we have shown 2-dimensional coordinate frames. This is appropriate for a large class of robotics problems, particularly for mobile robots which operate in a planar world. For other problems we require 3-dimensional coordinate frames to describe objects in our 3-dimensional world such as the pose of a flying or underwater robot or the end of a tool carried by a robot arm.

Fig. 2.3.

The point P can be described by coordinate vectors relative to either frame {A}, {B} or {C}. The frames are described by relative poses

> In relative pose composition we can check that we have our reference frames correct by ensuring that the subscript and superscript on each side of the ⊕ operator are matched. We can then cancel out the  intermediate subscripts and superscripts

>leaving just the end most subscript and superscript which are shown highlighted.

$$
J(\theta) = \frac 1 2 \sum_{i=1}^m (h_\theta(x^{(i)})-y^{(i)})^2
$$
