Test
#########################

.. rst:directive:: .. toggle-header:: class

"toggle-header" directive creates a block with a visible heading for the
hidden content. The heading can be clicked to view/hide the hidden content.
Optional attribute `class` adds css class for hidden content.
Required option `header` sets text of the heading of the hidden content.

Full example::

    .. toggle-header::
        :header: Example 1 **Show/Hide Code**

            Content for header


will be rendered like this:

.. toggle-header::
    :header: Example 1 **Show/Hide Code**

    Content for header

Generated HTML code:

.. code-block:: html

    <div class="toggle-header open">
        <p>Example <strong>Show/Hide Code</strong></p>
    </div>
    <div class="toggle-content docutils container">
        Content for header
    </div>

More examples
~~~~~~~~~~~~~

.. toggle-header::
    :header: Example 1 **Show/Hide Code**

    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
    incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis
    nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
    Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu
    fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
    culpa qui officia deserunt mollit anim id est laborum


.. toggle-header:: rubric
    :header: Example 2

    Sed ut perspiciatis, unde omnis iste natus error sit voluptatem
    accusantium doloremque laudantium, totam rem aperiam eaque ipsa, quae
    ab illo inventore veritatis et quasi architecto beatae vitae dicta
    sunt, explicabo. Nemo enim ipsam voluptatem, quia voluptas sit,
    aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos,
    qui ratione voluptatem sequi nesciunt, neque porro quisquam est, qui
    dolorem ipsum, quia dolor sit, amet, consectetur, adipisci velit, sed
    quia non numquam eius modi tempora incidunt, ut labore et dolore magnam
    aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum
    exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex
    ea commodi consequatur? Quis autem vel eum iure reprehenderit, qui in
    ea voluptate velit esse, quam nihil molestiae consequatur, vel illum,
    qui dolorem eum fugiat, quo voluptas nulla pariatur? At vero eos et
    accusamus et iusto odio dignissimos ducimus, qui blanditiis praesentium
    voluptatum deleniti atque corrupti, quos dolores et quas molestias
    excepturi sint, obcaecati cupiditate non provident, similique sunt in
    culpa, qui officia deserunt mollitia animi, id est laborum et dolorum
    fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam
    libero tempore, cum soluta nobis est eligendi optio, cumque nihil
    impedit, quo minus id, quod maxime placeat, facere possimus, omnis
    voluptas assumenda est, omnis dolor repellendus. Temporibus autem
    quibusdam et aut officiis debitis aut rerum necessitatibus saepe
    eveniet, ut et voluptates repudiandae sint et molestiae non recusandae.
    Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis
    voluptatibus maiores alias consequatur aut perferendis doloribus
    asperiores repellat.
